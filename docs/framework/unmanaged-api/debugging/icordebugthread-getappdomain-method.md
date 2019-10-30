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
ms.openlocfilehash: a845eed993914e02de34ec5c60ed232ccabc561e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133527"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="0fc54-102">ICorDebugThread::GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="0fc54-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="0fc54-103">Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, in der dieser ICorDebugThread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0fc54-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fc54-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fc54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fc54-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0fc54-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="0fc54-106">vorgenommen Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der dieser Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0fc54-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fc54-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0fc54-107">Requirements</span></span>  
 <span data-ttu-id="0fc54-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fc54-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fc54-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fc54-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fc54-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fc54-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fc54-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fc54-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
