---
title: ICorDebugChain::GetCaller-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0b5d702e9718ce6ac537beae67fc190b152b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405142"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="c6c62-102">ICorDebugChain::GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="c6c62-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="c6c62-103">Ruft die Kette, die diese Kette aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c6c62-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c62-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6c62-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6c62-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6c62-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="c6c62-106">[out] Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die aufrufende Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="c6c62-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="c6c62-107">Wenn diese Kette spontan aufgerufen wurde (wie der Fall wäre, wenn diese Kette oder der Debugger die Aufrufliste initialisiert), `ppChain` wird null sein.</span><span class="sxs-lookup"><span data-stu-id="c6c62-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6c62-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6c62-108">Remarks</span></span>  
 <span data-ttu-id="c6c62-109">Die aufrufende Kette kann in einem anderen Thread sein, wenn der Aufruf threadübergreifend gemarshallt wurde.</span><span class="sxs-lookup"><span data-stu-id="c6c62-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6c62-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6c62-110">Requirements</span></span>  
 <span data-ttu-id="c6c62-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6c62-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6c62-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6c62-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6c62-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6c62-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6c62-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6c62-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
