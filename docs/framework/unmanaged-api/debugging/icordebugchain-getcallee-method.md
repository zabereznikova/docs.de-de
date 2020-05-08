---
title: ICorDebugChain::GetCallee-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
ms.openlocfilehash: ba9a4e32216fd6fad285397bfc48fbc54f602b88
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894651"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="e55c7-102">ICorDebugChain::GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="e55c7-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="e55c7-103">Ruft die Kette ab, die von dieser Kette aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="e55c7-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e55c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e55c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e55c7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e55c7-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="e55c7-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das die aufgerufene Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="e55c7-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="e55c7-107">Wenn diese Kette derzeit ausgeführt wird (d. h., wenn diese Kette nicht darauf wartet, dass eine aufgerufene Kette `ppChain` zurückgegeben wird), ist NULL.</span><span class="sxs-lookup"><span data-stu-id="e55c7-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e55c7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e55c7-108">Remarks</span></span>  
 <span data-ttu-id="e55c7-109">Diese Kette wartet darauf, dass die aufgerufene Kette zurückkehrt, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="e55c7-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="e55c7-110">Die aufgerufene Kette kann sich in einem anderen Thread befinden, wenn Thread übergreifende Marshalling aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e55c7-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e55c7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e55c7-111">Requirements</span></span>  
 <span data-ttu-id="e55c7-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e55c7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e55c7-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e55c7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e55c7-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e55c7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e55c7-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e55c7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
