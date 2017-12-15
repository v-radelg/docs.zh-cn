---
title: "一般性指导原则"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |一般性指导原则"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a>一般性指导原则

本部分提供何时选择.NET 核心或.NET Framework 的摘要。 我们提供有关以下各节中的这些选项的更多详细信息。

当你有以下需求时应该用 .NET Core 与 Linux 或 Windows 容器来容器化 Docker 服务器应用程序：

-   用户有跨平台需求。 例如，你想要使用 Linux 和 Windows 容器。

-   你的应用程序体系结构基于微服务。

-   你需要以快速启动容器并需要每个容器，以实现更好的密度或每个硬件单位的多个容器内存占用较小，以便降低成本。

简单地说，在创建新容器化的 .NET 应用程序时，应考虑 .NET Core 作为默认选项。它有许多好处，并最能满足容器的基本原理和工作方式。

使用.NET Core 的另一个好处是你可以运行在同一台计算机中的应用程序的并行.NET 版本。 这一优势是为服务器或虚拟机不使用容器，更重要，因为容器隔离的.NET 应用程序所需的版本。 （只要它们是与基础操作系统兼容。）

在以下情景中，应对容器化 Docker 服务器应用程序使用 .NET Framework 和 Windows 容器：

-   你的应用程序当前使用.NET Framework 和 Windows 上具有强依赖关系。

-   你需要使用.NET Core 不支持的 Windows Api。

-   你需要使用第三方.NET 库或不可用于.NET 核心的 NuGet 包。

在 Docker 上使用 .NET Framework 可以最大限度减少部署问题，从而改善部署体验。[ *"直接迁移方案*](https://aka.ms/liftandshiftwithcontainersebook)对于最初使用ASP.NET WebForms、MVC Web 应用或 WCF（Windows Communication Foundation) 服务等传统 .NET Framework 开发的应用程序的容器化非常重要。

### <a name="additional-resources"></a>其他资源

-   **电子书：借助 Azure 和 Windows 容器使现有的 .NET Framework 应用程序更现代化**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)

-   **示例应用：可通过使用 Windows 容器使旧的 ASP.NET web 应用现代化**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)


>[!div class="step-by-step"]
[以前](index.md) [下一步] (net-核心-容器-scenarios.md)
