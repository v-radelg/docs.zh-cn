---
title: "终结点性能计数器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 157f0cc5d860841940b0850ca3895f82a12d47ce
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-performance-counters"></a>终结点性能计数器
终结点性能计数器可以捕获能够揭示终结点如何接受消息的数据。 如果使用性能监视器查看，可以在 `ServiceModelEndpoint 4.0.0.0` 性能对象下找到它们。 性能计数器实例使用以下模式命名：  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 它们所捕获的数据与针对单个操作收集的数据类似，不同之处仅在于在整个终结点中进行了聚合。  
  
> [!CAUTION]
>  性能计数器实例的名称长度存在限制。 当 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 计数器实例名称超出最大长度时，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 会用一个哈希值替换实例名称的一部分。  
  
## <a name="see-also"></a>另请参阅  
 [性能计数器](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
