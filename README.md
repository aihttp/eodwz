# 基于腾讯云 EdgeOne Pages 的短网址生成工具

[![Deploy with EdgeOne Pages](https://cdnstatic.tencentcs.com/edgeone/pages/deploy.svg)](https://edgeone.ai/pages/new?from=github&template=https://github.com/aihttp/eolocation)

使用 EdgeOne Pages 边缘函数搭建的短网址跳转平台

**短链生成**: 支持自定义或随机短链接标识符；
**访问统计**: 实时跟踪短链接的访问次数；
**管理界面**: Web 界面管理所有短链接

支持灵活配置各项环境变量：管理路径、管理密码、网站统计JS


##  项目特色

- **零静态文件**: 整个前端是一个自包含的 HTML 文档，直接从函数提供服务，无需单独的前端框架或构建过程
- **动态路由**: 单个 EdgeOne Function 作为通用路由器：
- **无服务器架构**: 基于 EdgeOne 的全球基础设施，确保低延迟和高可用性
- **简单部署**: 只需最少的设置，配置 KV 绑定并部署函数即可


### 部署步骤

【一】Fork本项目到你的仓库，在EO控制台创建项目-导入项目-框架预设 [Next] - 填写环境变量 - 开始部署

```
## 环境变量配置都是可选项，如果不配置则使用默认值

ADMIN_PATH=admin

ADMIN_PASS=admin123456

ANALYTICS_CODE=<script src="https://tongji.test.cn/script.js" data-website-id="2f696503-af46-4820-bce6-3b7c1160f9d0"></script>

UMAMI_HOST=https://tongji.test.cn

UMAMI_WEBSITE_ID=2f696503-af46-4820-bce6-3b7c1160f9d0
```

【二】在项目控制台-KV存储，新建命名空间 [任意名称] ，新建KV变量名称 [DWZ_KV] 绑定到该空间

【三】在项目控制台-构建部署-新建部署，浏览器访问默认预览域名或绑定你的自定义域名查看效果

  
### API 接口
- `POST /api/create` - 创建新的短链接
- `GET /api/links` - 获取所有短链接列表
- `DELETE /api/delete` - 删除指定的短链接

