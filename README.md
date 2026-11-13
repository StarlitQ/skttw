# 苍穹外卖学习项目

从桌面 skta 中整理的个人开发版本，整理日期：2026-11-13。
原目录保持不变；以后建议直接在这个新目录继续开发。

## 目录

- pom.xml、sky-common、sky-pojo、sky-server：原 sky-take-out 开发版本，保留完整依赖框架。
- frontend/admin-source：教程管理端 Vue 2 + TypeScript 源码。
- frontend/admin-preview-nginx：教程现成管理端页面和原 Nginx 配置；当前本机同时保留 nginx.exe，但二进制不提交 Git。
- frontend/miniapp-source：教程 uni-app 小程序源码，来自 project-rjwm-weixin-uniapp-develop-wsy.zip。
- frontend/miniapp-weixin：mp-weixin.zip 中的小程序材料，已去除压缩包内嵌套 Git 元数据。
- database/sky.sql：教程 day01 初始建库材料，不是当前 MySQL 数据库备份。
- docs/学习记录.md：原来的提交记录和相对初始代码的文件变更列表。

## 哪些是自己的开发版本

后端来自 C:\Users\zyq\Desktop\skta\sky-take-out，有 17 次学习提交，包含员工、分类、菜品、套餐、购物车和下单等功能。
保留原来的全部 Git 提交，并带入 SkyApplication.java 的未提交修改。
不能仅凭现有文件逐行区分原创与照教程实现，因此保留整个可继续开发的工程，另用学习记录列出初始版本后的改动。
没有混入“资料/day12/项目完整版代码”的教程答案，也没有复制全部课件。
桌面 Vue/vue-project1 是独立 Vue 3 计数器练习，与此 Vue 2 外卖管理端不对应，未合并。
frontend 和 database 均按教程材料标记，不将其归为个人原创。

## 本地使用

1. 在 IntelliJ IDEA 中打开根目录 pom.xml，作为 Maven 多模块项目导入。
2. 本机原 application-dev.yml 已保留，且从新提交的版本跟踪中排除；其他机器可复制 application-dev.example.yml 为 application-dev.yml 并填写实际配置。
3. 根据自己的 MySQL、Redis、OSS 和微信配置启动相应服务，再运行 com.sky.SkyApplication。数据库初始化前先确认目标数据库，避免覆盖现有数据。
4. 使用教程现成管理端：在 frontend/admin-preview-nginx 目录打开终端，运行 .\nginx.exe，然后访问 http://localhost/。原配置将 /api/ 转发至 http://localhost:8080/admin/。
5. 管理端源码可在 frontend/admin-source 查看，package.json 提供 npm run serve 和 npm run build。它使用老版本 Vue CLI 和 fibers，需要兼容的 Node 环境；本次没有安装依赖或验证构建。
6. 小程序材料的接口地址、AppID 和开发工具设置按当前环境调整；本次未启动小程序。

本次仅做文件整理与 Git 管理，没有启动业务服务、导入数据库或证明前后端已能联调。

## Git

根目录是唯一 Git 仓库，默认工作分支 main。原有 17 次历史保留，另新增整理提交。
尚未关联 GitHub 或其他远程仓库，没有上传文件。
常用操作：git status；git diff；git add <需要保存的文件>；git commit -m "说明修改"。
已忽略 target、node_modules、IDE 文件、日志和本地配置；测试源码不再被原有的宽泛规则排除。
注意：原提交历史曾跟踪 application-dev.yml。保留历史也保留了历史配置，未来公开上传前应单独检查历史凭据与第三方材料授权。
