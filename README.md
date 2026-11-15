## 目录

- pom.xml、sky-common、sky-pojo、sky-server：原skttw开发版本，保留完整依赖框架。
- frontend/admin-source：管理端Vue2+TypeScript源码。
- frontend/admin-preview-nginx：现成管理端页面和原Nginx配置
- frontend/miniapp-source：uni-app小程序源码
- frontend/miniapp-weixin：小程序材料
- database/sky.sql：初始建库材料,暂不完整

## 本地使用

1. 在IntelliJ IDEA中打开根目录pom.xml，作为 Maven 多模块项目导入。
2. 根据自己的 MySQL、Redis、OSS和微信配置启动相应服务，再运行com.sky.SkyApplication。数据库初始化前先确认目标数据库，避免覆盖现有数据。
3. 使用现成管理端：在 frontend/admin-preview-nginx目录打开终端，运行.\nginx.exe，然后访问 http://localhost/。原配置将 /api/ 转发至 http://localhost:8080/admin/。
4. 管理端源码可在 frontend/admin-source 查看，package.json 提供npm run serve和npm run build。它使用老版本 Vue CLI 和fibers，需要兼容的 Node 环境。
5. 小程序材料的接口地址、AppID 和开发工具设置按环境调整
