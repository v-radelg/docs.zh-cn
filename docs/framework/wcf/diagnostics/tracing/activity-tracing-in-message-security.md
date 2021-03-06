---
title: "消息安全中的活动跟踪"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68862534-3b2e-4270-b097-8121b12a2c97
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 60156e284c55d765de417fe891185d1aba720816
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="activity-tracing-in-message-security"></a>消息安全中的活动跟踪
本主题描述用于安全处理的活动跟踪，这些活动跟踪发生在以下三个阶段。  
  
-   协商/SCT 交换。 这可能发生在传输层（通过二进制数据交换）或消息层（通过 SOAP 消息交换）。  
  
-   消息加密/解密（带有签名验证和身份验证）。 跟踪出现在环境活动（通常为“进程操作”）中。  
  
-   授权和验证。 这可能在本地发生，或是在终结点之间进行通信时发生。  
  
## <a name="negotiationsct-exchange"></a>协商/SCT 交换  
 在协商/SCT 交换阶段，将在客户端上创建两种活动类型：“设置安全会话”和“关闭安全会话”。 “设置安全会话”包括对 RST/RSTR/SCT 消息交换的跟踪，而“关闭安全会话”包括对“取消”消息的跟踪。  
  
 在服务器上，RST/RSTR/SCT 的每个请求/答复都出现在它自己的活动中。 如果`propagateActivity` = `true`在服务器和客户端上，在服务器上的活动具有相同的 ID，并在"设置安全会话"查看通过服务跟踪查看器时出现在一起。  
  
 此活动跟踪模型对于用户名/密码身份验证、证书身份验证和 NTLM 身份验证都有效。  
  
 下表列出了用于协商和 SCT 交换的活动和跟踪。  
  
||发生协商/SCT 交换的时间|活动|跟踪|  
|-|-------------------------------------------------|----------------|------------|  
|安全传输<br /><br /> （HTTPS、SSL）|在接收到第一个消息时。|在环境活动中发出跟踪。|交换跟踪<br />-已建立安全通道<br />-获取共享机密。|  
|安全消息层<br /><br /> (WSHTTP)|在接收到第一个消息时。|在客户端上：<br /><br /> -"设置安全会话"超出"进程操作"的该第一条消息，每个请求/答复的 RST/RSTR/SCT。<br />-"关闭安全会话"，取消交换，超出的"关闭代理活动"。 此活动可能源自其他某个环境活动，具体取决于关闭安全会话的时间。<br /><br /> 在服务器上：<br /><br /> 的每个请求/答复的 RST/SCT/取消服务器上的"进程操作"活动一个。 如果`propagateActivity` = `true`、 RST/RSTR/SCT 活动与"设置安全会话"，而取消与从客户端的"关闭"活动合并。<br /><br /> “设置安全会话”有两个阶段：<br /><br /> 1.身份验证协商。 如果客户端已拥有正确的凭据，则此阶段是可选的。 可以通过安全传输或通过消息交换完成此阶段。 在后一种情况下，可能发生 1 次或 2 次 RST/RSTR 交换。 对于这些交换，将在新的请求/答复活动中发出跟踪，如同以前设计的一样。<br />2.安全会话建立 (SCT)，此阶段会发生一次 RST/RSTR 交换。 此阶段具有与之前所述相同的环境活动。|交换跟踪<br />-已建立安全通道<br />-获取共享机密。|  
  
> [!NOTE]
>  在混合安全模式中，协商身份验证发生在二进制交换中，但 SCT 发生在消息交换中。 在纯粹的传输模式中，协商仅发生在传输中，并且没有其他活动。  
  
## <a name="message-encryption-and-decryption"></a>消息加密和解密  
 下表列出了消息加密/解密以及签名身份验证的活动和跟踪。  
  
||安全传输<br /><br /> （HTTPS、SSL）和安全消息层<br /><br /> (WSHTTP)|  
|-|---------------------------------------------------------------------------------|  
|发生消息加密/解密以及签名身份验证的时间|在接收到消息时|  
|活动|在客户端和服务器上的“进程操作”活动中发出跟踪。|  
|跟踪|-sendSecurityHeader （发送方）：<br />登录消息<br />-加密请求数据<br />-receiveSecurityHeader （接收方）：<br />-验证签名<br />-解密响应数据<br />身份验证|  
  
> [!NOTE]
>  在纯粹的传输模式中，消息加密/解密仅发生在传输中，并且没有其他活动。  
  
## <a name="authorization-and-verification"></a>授权和验证  
 下表列出了授权的活动和跟踪。  
  
||发生授权的时间|活动|跟踪|  
|-|-------------------------------------|----------------|------------|  
|本地（默认）|在服务器上对消息进行解密之后|在服务器上的“进程操作”活动中发出跟踪。|已授权用户。|  
|远程|在服务器上对消息进行解密之后|在由“进程操作”活动调用的新活动中发出跟踪。|已授权用户。|
