---
title: "ICorDebugProcess::EnumerateAppDomains 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.EnumerateAppDomains
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5233dd80750afb82a2e2a8e9675867f6decfa8f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="98fae-102">ICorDebugProcess::EnumerateAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="98fae-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="98fae-103">枚举在此过程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="98fae-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98fae-104">语法</span><span class="sxs-lookup"><span data-stu-id="98fae-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98fae-105">参数</span><span class="sxs-lookup"><span data-stu-id="98fae-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="98fae-106">[out]指向的地址的指针[ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) ，它是此进程中的应用程序域的枚举数。</span><span class="sxs-lookup"><span data-stu-id="98fae-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98fae-107">备注</span><span class="sxs-lookup"><span data-stu-id="98fae-107">Remarks</span></span>  
 <span data-ttu-id="98fae-108">可以使用此方法之前[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="98fae-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98fae-109">要求</span><span class="sxs-lookup"><span data-stu-id="98fae-109">Requirements</span></span>  
 <span data-ttu-id="98fae-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98fae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98fae-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98fae-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98fae-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98fae-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98fae-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98fae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>