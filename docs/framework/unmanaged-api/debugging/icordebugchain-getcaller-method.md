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
ms.openlocfilehash: 0f616b3bae48a972c0fc8935c35add7d844a7364
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730109"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="377e7-102">ICorDebugChain::GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="377e7-102">ICorDebugChain::GetCaller Method</span></span>

<span data-ttu-id="377e7-103">Ruft die Kette ab, die diese Kette aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="377e7-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="377e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="377e7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="377e7-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="377e7-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die aufrufende Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="377e7-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="377e7-107">Wenn diese Kette spontan aufgerufen wurde (wie es der Fall wäre, wenn diese Kette oder der Debugger die Aufruf Stapel initialisiert hat), ist `ppChain` NULL.</span><span class="sxs-lookup"><span data-stu-id="377e7-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="377e7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="377e7-108">Remarks</span></span>  

 <span data-ttu-id="377e7-109">Die aufrufende Kette kann sich in einem anderen Thread befinden, wenn der Aufruf über Threads hinweg gemarshallt wurde.</span><span class="sxs-lookup"><span data-stu-id="377e7-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377e7-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="377e7-110">Requirements</span></span>  

 <span data-ttu-id="377e7-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="377e7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="377e7-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="377e7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="377e7-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="377e7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="377e7-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="377e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
