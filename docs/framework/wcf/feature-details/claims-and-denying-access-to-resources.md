---
title: "声明和拒绝访问资源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 00d6a797b8099313c15d075457ee757c1f22f744
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="claims-and-denying-access-to-resources"></a>声明和拒绝访问资源
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 支持基于声明的授权机制。 在基于是否存在声明来允许访问资源的同时，系统通常也基于是否存在声明来拒绝访问资源。 这样的系统应该在查找导致允许访问的声明之前先检查 <xref:System.IdentityModel.Policy.AuthorizationContext> 是否存在导致拒绝访问的声明。  
  
 例如，对于具有类型为 `Age`、权限为 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 和资源值为 `Under 21` 的声明的任何用户，仅当该标识同时也具有类型为 `Name`、权限为 <xref:System.IdentityModel.Claims.Rights.Identity%2A> 和资源值为 `Mallory` 的声明时，系统才会拒绝其访问资源。 换言之，对于年龄不到 21 岁的任何人，系统拒绝其访问资源，如果姓名为 Mallory，则系统允许其访问资源。 为了正确地实现此语义，必须首先查找 `Age` 声明，然后确定年龄是否低于 21 岁。 否则，如果 Mallory 不到 21 岁，则仅基于 `Name` 声明授予对资源的访问权限。  
  
## <a name="see-also"></a>另请参阅  
 [管理声明和使用标识模型的授权](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [声明和令牌](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
