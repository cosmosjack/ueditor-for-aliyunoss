# ueditor-for-aliyunoss
百度编辑器支持阿里云的OSS,来达到多个服务器同步图片资源。
# 环境：
  apache2.4  php5.6  mysql1.0+ 
  
  
# 问题描述：
  两台服务器以上时，用百度编辑器编写的文章里边所添加的图片，不能同步到另外几个服务器中（就算用inotify+rsync实时同步也还是会出问题），所以这时候就需要
用到云存储了。


# 解决方案：
  使用阿里云的OSS  
  
  
# 配置步骤 
 # 涉及文件 
          conf.inc.php 
          Uploader.class.php
          action_list.php
          uploadfile.php 可以不用修改
          
 <hr>         
          <ul>
  <li> oss apikey  和秘钥配置  《conf.inc.php》  在代码的前两个 我标有注释</li>
  <li> PDO 的配置  《uploader.class.php》《action_list.php》  在注释 PDO配置下边 修改</li>
   <li>上传文件的新的文件名字的配置 《uploadfile.php》    在 public function getSysSetPath() 方法里边 </li>
  <li>
    数据表的 字段  id  int 主键  url  varchar(200)   mtime varchar(15)  size varchar(15) 
  </li>
    </ul>
     <hr>
配置好后就可以直接访问 测试了

<ul>
<li>说明1 由于时间较紧迫 没做太多优化 （其中 所有文件中 define 的所有配置参数 你可以根据自己需求 做一个统一的配置文件来加载） </li>
<li>说明2 PDO插件中的 class pdo 中的缓存方法时没有用的（只做了一个简化版的）</li>
</ul>

# 作者 
神秘剑派 大师兄  xzc 技能    QQ 997823131
  
