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
ms.openlocfilehash: a6d26924773e6ad505975402ec3ace150d02cc3a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894617"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="3097d-102">ICorDebugChain::GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="3097d-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="3097d-103">Ruft die Kette ab, die diese Kette aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="3097d-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3097d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3097d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3097d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3097d-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="3097d-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die aufrufende Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="3097d-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="3097d-107">Wenn diese Kette spontan aufgerufen wurde (wie es der Fall wäre, wenn diese Kette oder der Debugger die Aufruf Stapel initialisiert hat `ppChain` ), ist NULL.</span><span class="sxs-lookup"><span data-stu-id="3097d-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3097d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3097d-108">Remarks</span></span>  
 <span data-ttu-id="3097d-109">Die aufrufende Kette kann sich in einem anderen Thread befinden, wenn der Aufruf über Threads hinweg gemarshallt wurde.</span><span class="sxs-lookup"><span data-stu-id="3097d-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3097d-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3097d-110">Requirements</span></span>  
 <span data-ttu-id="3097d-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3097d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3097d-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3097d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3097d-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3097d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3097d-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3097d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
