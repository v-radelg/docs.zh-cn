---
title: MsmqTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 572a19723583a6bc717a71b3b46040148f29e1cd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement
MsmqTransportBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a>方法  
 MsmqTransportBindingElement 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 MsmqTransportBindingElement 类具有以下属性：  
  
### <a name="maxpoolsize"></a>MaxPoolSize  
 数据类型：sint32  
  
 访问类型：只读  
  
 包含内部 MSMQ 消息对象的池的最大大小。  
  
### <a name="queuetransferprotocol"></a>QueueTransferProtocol  
 数据类型：String  
  
 访问类型：只读  
  
 一个枚举值，指示此绑定使用的排队通信通道传输。  
  
### <a name="useactivedirectory"></a>UseActiveDirectory  
 数据类型：Boolean  
  
 访问类型：只读  
  
 返回一个布尔值，该值指示是否应该使用 Active Directory 来转换队列地址。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
