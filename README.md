# bmobsdk
base on bmobsdk v3.5.1
已经配置好permission，gradle依赖

BmobSDK_v3.5.0需要依赖rxjava（1.1.6）、rxandroid(1.2.0)、gson(2.6.2)、okhttp3（3.4.1）、okio（1.7.0）及libbmob.so库

usage

1、

      repositories {
        // ...
        maven { url "https://jitpack.io" }
    }

    compile 'com.github.djun100:BmobSDK:4ee82e61b1258fa8971b87ec3898a3dacf46b329'
2、in application
    
	/**
	 * 初始化文件配置
	 * @param context
	 */
	public static void initConfig(Context context) {
		BmobConfiguration config = new BmobConfiguration.Builder(context).customExternalCacheDir("Smile").build();
		BmobPro.getInstance(context).initConfig(config);
	}
3、in 启动页activity

		//第一：默认初始化
        Bmob.initialize(this, "Your Application ID");

        //第二：自v3.4.7版本开始,设置BmobConfig,允许设置请求超时时间、文件分片上传时每片的大小、文件的过期时间(单位为秒)，
        //BmobConfig config =new BmobConfig.Builder(this)
        ////设置appkey
        //.setApplicationId("Your Application ID")
        ////请求超时时间（单位为秒）：默认15s
        //.setConnectTimeout(30)
        ////文件分片上传时每片的大小（单位字节），默认512*1024
        //.setUploadBlockSize(1024*1024)
        ////文件的过期时间(单位为秒)：默认1800s
        //.setFileExpiration(2500)
        //.build();
        //Bmob.initialize(config);