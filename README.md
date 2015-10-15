# bmobsdk
base on bmobsdk v3.4.4
已经配置好permission，加好jar包
usage

1、

      repositories {
        // ...
        maven { url "https://jitpack.io" }
    }

    compile 'com.github.djun100:BmobSDK:11054f373bc0357c90045c9d5bf3502e045e15f5'
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

    Bmob.initialize(getApplicationContext(),APPID);
