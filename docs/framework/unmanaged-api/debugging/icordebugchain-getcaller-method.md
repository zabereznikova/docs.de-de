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
ms.openlocfilehash: 5a07550d44857526e8ab4ded9f1827ef12e3bba4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192134"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="ea156-102">ICorDebugChain::GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="ea156-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="ea156-103">Ruft die Kette ab, die diese Kette aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="ea156-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea156-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea156-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea156-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea156-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="ea156-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die aufrufende Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="ea156-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="ea156-107">Wenn diese Kette spontan aufgerufen wurde (wie es der Fall wäre, wenn diese Kette oder der Debugger die Aufruf Stapel initialisiert hat), wird `ppChain` NULL sein.</span><span class="sxs-lookup"><span data-stu-id="ea156-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea156-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea156-108">Remarks</span></span>  
 <span data-ttu-id="ea156-109">Die aufrufende Kette kann sich in einem anderen Thread befinden, wenn der Aufruf über Threads hinweg gemarshallt wurde.</span><span class="sxs-lookup"><span data-stu-id="ea156-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea156-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea156-110">Requirements</span></span>  
 <span data-ttu-id="ea156-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea156-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea156-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea156-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea156-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea156-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea156-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea156-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
