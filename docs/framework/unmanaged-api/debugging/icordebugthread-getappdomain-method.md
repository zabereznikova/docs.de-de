---
title: ICorDebugThread::GetAppDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetAppDomain
helpviewer_keywords:
- GetAppDomain method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetAppDomain method [.NET Framework debugging]
ms.assetid: 415b3d34-8b35-4b60-a318-140646cc83f8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c235bc0294b967e26766a095b85c5acf0f27cff9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="42cd8-102">ICorDebugThread::GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="42cd8-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="42cd8-103">Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne, in der dieser ICorDebugThread derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="42cd8-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42cd8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42cd8-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42cd8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="42cd8-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="42cd8-106">[out] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der dieser Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="42cd8-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42cd8-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42cd8-107">Requirements</span></span>  
 <span data-ttu-id="42cd8-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42cd8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42cd8-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42cd8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42cd8-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42cd8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42cd8-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42cd8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
