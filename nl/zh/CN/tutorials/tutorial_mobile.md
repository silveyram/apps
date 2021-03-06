---

copyright:
  years: 2016, 2017, 2018
lastupdated: "2018-08-21"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 使用初学者工具包创建移动应用程序
{: #tutorial}

{{site.data.keyword.Bluemix}} 提供了移动入门模板工具包，可帮助您快速创建移动应用程序。从 App Service 入门模板工具包中选择语言、框架和工具，以开始使用预配置的定制应用程序。在本教程中，您可以了解如何安装所需的工具，如何在本地构建和运行应用程序，以及如何将应用程序部署到云上。
{: shortdesc}

## 步骤 1. 安装工具
{: #install-tools}

安装 [Developer Tools ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools){: new_window}。

Docker 作为 Developer Tools 的一部分安装。Docker 必须在运行，构建命令才有效。您必须创建 Docker 帐户、运行 Docker 应用程序并登录。

## 步骤 2. 使用 {{site.data.keyword.dev_console}} 创建应用程序
{: #create-devex}

1. 在 {{site.data.keyword.Bluemix}} 中创建 {{site.data.keyword.dev_console}} 应用程序。
2. 在 {{site.data.keyword.dev_console}} 中的[入门模板工具包 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://console.ng.bluemix.net/developer/appservice/starter-kits/) 页面中，根据您需要的功能来选择入门模板工具包。例如，对于 Watson Language 应用程序，选择 **Swift Kitura**。
3. 输入应用程序名称。对于本教程，请使用 `WatsonApp`。
4. 选择语言平台。对于本教程，请使用 `Swift`。
5. 选择语言和框架。一些入门模板工具包可能只有一种语言可用。
6. 选择价格套餐。对于本教程，可以使用免费选项。
7. 单击**创建**。

## 步骤 3. 添加资源（可选）
{: #add-services}

可以添加用于通过 Watson 的认知功能增强应用程序的资源，也可以添加移动服务或安全服务。对于本教程，请添加用于管理数据的位置。

1. 在 App Service 窗口中，单击**添加资源**。
2. 选择所需的服务类型。例如，选择**数据** > **下一步** > **Cloudant** > **下一步**。
3. 选择价格套餐。对于本教程，可以使用免费选项。
4. 单击**创建**。

## 步骤 4. 创建 DevOps 工具链
{: #add-toolchain}

启用工具链会为应用程序创建基于团队的开发环境。创建工具链时，App Service 将创建 Git 存储库，在其中可以查看源代码，克隆应用程序以及创建和管理问题。您还有权访问专用的 GitLab 环境和持续交付管道。可以根据您选择的部署平台（无论是 Kubernetes 还是 Cloud Foundry）对其进行定制。

某些应用程序已启用了持续交付。您可以启用持续交付以通过 Delivery Pipeline 和 GitHub 来自动执行构建、测试和部署。

1. 在 App Service 窗口中，单击**部署到云**。
2. 选择部署方法。根据您所选方法的指示信息来设置部署方法。

    * 部署到 Kubernetes 集群。创建主机集群（称为工作程序节点）来部署和管理高可用性应用程序容器。可以创建集群或部署到现有集群。

    * 使用 Cloud Foundry 进行部署，在其中不需要管理底层基础架构。

## 步骤 5. 在本地构建和运行应用程序
{: #build-run}

在最后一步中将应用程序部署到云后，即创建了工具链。工具链会为应用程序创建 Git 存储库，在其中可以查找代码。请执行以下步骤来访问存储库。在将应用程序推送到云之前，可以在本地构建应用程序以进行测试。

1. 在 App Service 窗口中，单击**下载代码**或**克隆存储库**以本地使用代码。
2. 将应用程序导入到集成开发环境中。
3. 修改代码。
4. 通过添加个人访问令牌来设置 [Git 认证](/docs/services/ContinuousDelivery/git_working.html#git_authentication)。
5. 登录到 {{site.data.keyword.Bluemix}} 命令行界面。如果组织使用的是联合登录，请使用 `-sso` 选项。

  ```bash
  ibmcloud login -sso
  ```
  {: pre}

6. 设置组织和空间目标。

  ```bash
  ibmcloud target --cf
  ```
  {: pre}

7.  获取凭证。

  ```bash
  ibmcloud dev get-credentials
  ```
  {: pre}

8. 确保 Docker 正在运行，然后在目录中的本地开发容器中构建应用程序。

  ```bash
  ibmcloud dev build
  ```
  {: pre}

9. 在本地开发容器中运行应用程序。

  ```bash
  ibmcloud dev run
  ```
  {: pre}

10.  打开浏览器并转至 `http://localhost:3000`。您的端口号可能有所不同，具体取决于所选的运行时。

### 在 Xcode 中运行 Swift 应用程序
{: #run_swift}

1. 在 Markdown 查看器中打开 `README.md` 文件，以查看用于配置应用程序的步骤。
2. 打开终端并浏览到应用程序文件夹，然后运行以下命令：
    1. 如果需要设置 CocoaPods 存储库，请运行 `pod setup`。
    2. 如果需要更新现有 pod，请运行 `pod update`。
    3. 运行 `pod install`，为应用程序安装 pod。
3. 打开 `<appname>.xcworkspace` Xcode 工作空间。
4. 运行应用程序。

### 在 Xcode 中运行 Cordova 应用程序
{: #run_cordova_xcode}

如果选择使用 Cordova 作为实现语言，请遵循以下指示信息进行操作。

1. 在 Markdown 查看器中打开 `README.md` 文件以配置应用程序。
2. 在 Xcode 中打开 `platforms/ios` 应用程序。
3. 运行应用程序。

### 在 Android Studio 中运行 Cordova 应用程序
{: #run_cordova_studio}

如果选择使用 Cordova 作为移动应用程序的平台，请使用此部分。

1. 解压缩 `BasicProfile-Cordova.zip` 文件。
2. 在 Markdown 查看器中打开 `README.md` 文件以配置应用程序。
3. 在 Android Studio 中打开 `platforms/android` 应用程序。
4. 运行应用程序。

### 在 Android Studio 中运行 Android 应用程序
{: #run_android}

如果选择使用 Android 作为移动应用程序的平台，请使用此部分。

1. 在 Markdown 查看器中打开 `README.md` 文件以配置应用程序。
2. 在 Android Studio 中打开 `BasicProject-Android` 应用程序。
3. 运行应用程序。

## 步骤 6. 部署应用程序
{: #deploy}

### 使用工具链进行部署

有多种方式可以将应用程序部署到 {{site.data.keyword.cloud_notm}}，但 DevOps 工具链是部署生产应用程序的最佳方式。通过 DevOps 工具链，您可以轻松地自动部署到许多环境，并快速添加监视、日志记录和警报服务，以帮助在应用程序增长时对其进行管理。

使用正确配置的工具链，每次合并到存储库中的主分支时，会自动启动构建/部署周期。在 {{site.data.keyword.cloud_notm}} 开发者仪表板中创建的所有工具链都将配置为自动部署。


您还可以通过 DevOps 工具链来手动部署应用程序：

1. 在“应用程序详细信息”窗口中，单击**查看工具链**。

2. 单击 **Delivery Pipeline**，在其中可以启动构建、管理部署以及查看日志和历史记录。

### 使用 {{site.data.keyword.dev_cli_short}} 进行部署

要将应用程序部署到 Cloud Foundry，请输入以下命令：

```
ibmcloud dev deploy
```
{: pre}

要将应用程序部署到 Kubernetes 集群，请输入以下命令：

```
ibmcloud dev deploy --target <container>
```
{: pre}

## 步骤 7. 验证应用程序是否在运行
{: #verify}

部署应用程序后，DevOps 管道或命令行会将您指向该应用程序的 URL，例如 `abc-devhost.mybluemix.net`。在浏览器中转至该 URL。
