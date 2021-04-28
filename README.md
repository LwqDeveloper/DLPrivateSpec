# DLPrivateSpec
私有Pod库
## 1.创建私有spec repo也就是配置仓库
### pod repo add PrivateSpec(私有配置仓库名称) 私有配置仓库git地址(ssh地址比较好一些)

## 2.创建Pod项目工程
### pod lib create CCLibTest

### 3.提交代码
### git init
### git add .
### git commit -m 'init'
### git remote add origin ---  添加仓库
### git merge master --allow-unrelated-histories    master -> main
### git pull 
### git push

## 4.tag
### git tag -m 'init' '0.0.1'
### git push --tags

## 5.验证podspec，进入CCLibTest目录
### pod spec lint --allow-warnings

## 6.CCLibTest.podspec上传到私有配置仓库PrivateSpec
### pod repo push PodPrivate CCLibTest.podspec --verbose --use-libraries --allow-warnings
  
  

    Pod::Spec.new do |s|
      s.name             = 'CCLibTest'
      s.version          = '1.0.0'
      s.summary          = 'A short description of CCLibTest.'
      s.description      = <<-DESC
    TODO: Add long description of the pod here.
                           DESC

      s.homepage         = 'https://xxxx.com'
      s.license          = { :type => 'MIT', :file => 'LICENSE' }
      s.author           = { 'w_sen' => 'xxxx@xxxx.com' }
      s.source           = { :git => 'https://xxxx.com/xxxx/CCLibTest.git', :tag => s.version.to_s }
      s.ios.deployment_target = '8.0'
      s.source_files = 'CCLibTest/Classes/**/*'
    end

    查阅了下解释，不太全，其实可以自行搜索，

    s.name ：pod search 搜索的关键词,注意这里一定要和.podspec的名称一样
    s.version ：版本号，每一个版本对应一个tag
    s.summary : 简介
    s.homepage : 项目主页地址
    s.license : 许可证
    s.author : 作者
    s.source : 项目的地址
    s.source_files : 需要包含的源文件
    s.resources: 资源文件
    s.dependency ：依赖库
    s.ios.deployment_target = '8.0'  : 支持的pod最低版本

    s.source_files = 'CCLibTest/Classes/**/*'
    *匹配所有文件 **匹配所有子目录
  
  

## 参考链接https://my.oschina.net/snOS/blog/2998642
