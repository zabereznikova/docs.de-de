---
title: ICorDebugThread::GetAppDomain-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da473ed176ab6c69ed974d5f28b22fc8eb30c6af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762518"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="6395f-102">ICorDebugThread::GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="6395f-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="6395f-103">Ruft einen Schnittstellenzeiger an die Anwendungsdomäne, in der dieser ICorDebugThread derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6395f-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6395f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6395f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6395f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6395f-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="6395f-106">[out] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der der Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6395f-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6395f-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6395f-107">Requirements</span></span>  
 <span data-ttu-id="6395f-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6395f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6395f-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6395f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6395f-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6395f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6395f-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6395f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
