# 在DLL文件里使用Log4net,适用于插件DLL，服务DLL

#region  加载Log4Net组件
    try
    {
        //获取配置文件全称
        string str = System.Reflection.Assembly.GetExecutingAssembly().GetName().Name + ".Plugin.config";
        //读取配置文件
        System.IO.Stream stream = System.Reflection.Assembly.GetExecutingAssembly().GetManifestResourceStream(str);
        log4net.Config.XmlConfigurator.Configure(stream);
    }
    catch (Exception ex)
    {
        throw new Exception(ex.Message);
    }
#endregion

# 项目里面不要忘记把 Plugin.config 的属性 “生成操作” 改成 “嵌入的资源”！
