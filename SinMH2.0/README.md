# 安装指南
1. 上传`src`目录到服务器，上传`vendor`目录到`src`目录下
1. 复制`src/environments/prod`目录下的全部目录和文件到src目录下，
1. 创建空数据库，并配置`src/common/config/main-local.php`下`db`数据库`dsn`,`username`,`password`，根据需要配置 `mailer | sinmhSdk | authClientCollection`相关账号密码
1. 配置下列`main-local.php`下的`cookieValidationKey`，设置为16~32位随机字符串

  ```
'backend/config/main-local.php';
'admin/config/main-local.php';
'api/config/main-local.php';
'frontend/config/main-local.php';
'member/config/main-local.php';
'console/config/main-local.php';
```
5. 设置下列目录777权限

 ```
'common/runtime';
'console/runtime';
'backend/runtime';
'backend/web/assets';
'admin/runtime';
'admin/web/assets';
'api/runtime';
'api/web/assets';
'member/runtime';
'member/web/assets';
'frontend/runtime';
'frontend/web/assets';
'frontend/web/js';
```
6. 配置web服务器（IIS/Apache/Nginx），设置域名指向；

 ```
前台页面指向src/fontend/web;
后台指向src/admin/web;
会员中心指向src/member/web;
API指向src/api/web;
系统管理指向src/backend/web;
```
7. 依据上一步配置`src/common/config/params-local.php`下的`domain`、`javascript`、`collect`相关域名信息、采集映射信息，其余配置参数可依据实际需要调整
8. 使用系统管理`backend`安装数据库
8. 使用系统管理`backend`添加后台管理超级管理员
8. 配置任务计划：详见[任务计划](任务计划.md)
