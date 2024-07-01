# 快速部署MultiTag媒资系统

## 概述

MultiTag媒资系统是基于媒体资料管理的多功能的综合性媒资系统，支持综合制作系统、新闻直播系统、音频系统提交的素材和节目入库，并对素材、通稿、待播节目、播后节目进行分门别类的处理等多种业务流程。
MultiTag媒资系统可以提供素材/通稿入库、节目入库、多模态检索、智能编目、在线预览、主题资料库、智能下载、分组权限、主敏感内容过滤、文件或介质下载等多种类型的服务，实现资源最大限度的共享，最高效率的利用。


## 计费说明

MultiTag媒资系统在计算巢上的费用主要涉及：所选vCPU与内存规格、磁盘容量、公网带宽、OSS存储、媒体处理（包含转码服务、智能能力服务）、智能媒体生产（包含一键成片、智能检索等服务）。
计费方式包括包年包月、按量付费，ECS及流量预估费用在创建实例时可实时看到，OSS存储、媒体处理使用、智能媒体服务费用按量付费，具体请见：

OSS产品价格：https://www.aliyun.com/price/product?spm=5176.7933691.J_5253785160.5.28a62c4765ojgU#/oss/detail

媒体处理产品价格：https://www.aliyun.com/price/product?spm=5176.7933691.J_5253785160.5.28a62c4765ojgU#/mts/detail/mts

智能媒体生产产品价格:https://help.aliyun.com/zh/ims/billing-overview



## 部署架构

<img width="327" alt="image" src="https://github.com/aliyun-computenest/quickstart-multitag/assets/158254627/2d126da4-1a47-466b-9b37-38ee4a9bcd5a">


## RAM账号所需权限



Demo服务需要对ECS、VPC等资源进行访问和创建操作，若您使用RAM用户创建服务实例，需要在创建服务实例前，对使用的RAM用户的账号添加相应资源的权限。添加RAM权限的详细操作，请参见[为RAM用户授权](https://help.aliyun.com/document_detail/121945.html)。所需权限如下表所示。


| 权限策略名称                    | 备注                                                         |
| ------------------------------- | ------------------------------------------------------------ |
| AliyunComputeNestUserFullAccess | 管理计算巢服务（ComputeNest）的用户侧权限，该权限可以查看用户侧的视图，也可以对用户侧的视图进行编辑。 |
| AliyunECSFullAccess             | 管理云服务器服务（ECS）的权限                                |
| AliyunVPCFullAccess             | 管理专有网络（VPC）的权限。                                  |
| AliyunTagAdministratorAccess    | 管理标签服务（TAG）和所有阿里云产品标签的权限。              |
| AliyunCloudMonitorFullAccess    | 管理云监控（CloudMonitor）的权限                             |
| AliyunROSFullAccess             | 管理资源编排服务（ROS）的权限                                |
| AliyunOSSFullAccess             | 管理对象存储服务（OSS）权限                                  |
| AliyunMTSFullAccess             | 管理媒体转码服务(MTS)的权限                                  |
| AliyunICEFullAccess             | 管理智能媒体服务的权限                                       |

# 部署流程

### 第一步：检查服务是否开通

部署MultiTag服务除开通ECS服务外，还需要开通对象存储OSS服务、媒体处理MPS服务、智能媒体服务。

对象存储OSS服务：[OSS管理控制台 (aliyun.com)](https://oss.console.aliyun.com/overview?spm=5176.7933691.J_5253785160.3.55ed2c475hX9ZA)

媒体处理MPS服务：[媒体处理 MPS (aliyun.com)](https://mps.console.aliyun.com/overview)

智能媒体服务：[智能媒体服务IMS (aliyun.com)](https://ice.console.aliyun.com/summary)

### 第二步：进行服务配置配置

1. 设置服务实例名称；
2. 选择部署地域（可选择上海、杭州、北京区域，可以选择离自己最近的城市，如无特殊要求，保持默认即可）；
3. 设置存储空间名称（MultiTag媒资系统内所有素材均会存储至该存储空间内）；
4. 设置系统管理员密码（MultiTag媒资系统管理员admin用户密码）；
5. 选择ECS服务器配置，配置服务器密码；
6. 选择ECS服务器所在的可用区及VPC实例

### 第三步：创建服务

1. 在服务确认页面，勾选同意服务条款，点击“立即创建”，进行付款流程。
2. 当出现提交成功提示，说明服务已经开始创建，点击“去列表查看”，可以看到服务正在部署中。 [![1.jpg](https://github.com/aliyun-computenest/quickstart-minecraft/raw/main/docs/3.jpg)](https://github.com/aliyun-computenest/quickstart-minecraft/blob/main/docs/3.jpg)

### 第四步：进入实例详情

1. 服务约5分钟完成创建，当服务的状态变成“已部署”，点击服务实例ID进入服务详情。
2. 浏览器输入服务详情内的访问页面，或者输入服务实例详情-资源-弹性公网IP地址加8000端口访问MultiTag页面。
<img width="1228" alt="image-20240701150205127" src="https://github.com/aliyun-computenest/quickstart-multitag/assets/158254627/76f2cc7b-415e-437f-bd2a-36b5473c092c">

# 系统使用

浏览器输入服务详情内的访问页面，初始账号admin，密码为部署时设置的系统管理员密码，输入验证码后即可登陆系统。系统使用详见系统用户使用手册。

<img width="1435" alt="image-20240701150608265" src="https://github.com/aliyun-computenest/quickstart-multitag/assets/158254627/496ec5a0-57a7-4949-816c-5052f1d7db70">


<img width="1438" alt="image-20240701150659835" src="https://github.com/aliyun-computenest/quickstart-multitag/assets/158254627/1024529a-cf40-4533-a604-ea8a71338845">


