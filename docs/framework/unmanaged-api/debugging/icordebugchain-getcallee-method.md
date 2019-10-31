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
ms.openlocfilehash: 5d28af09faae84b0482d438ae33f593f250490c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196341"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="04c3e-102">ICorDebugChain::GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="04c3e-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="04c3e-103">Ruft die Kette ab, die von dieser Kette aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="04c3e-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c3e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="04c3e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04c3e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="04c3e-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="04c3e-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das die aufgerufene Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="04c3e-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="04c3e-107">Wenn diese Kette derzeit ausgeführt wird (d. h., wenn diese Kette nicht darauf wartet, dass eine aufgerufene Kette zurückgegeben wird), ist `ppChain` NULL.</span><span class="sxs-lookup"><span data-stu-id="04c3e-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04c3e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04c3e-108">Remarks</span></span>  
 <span data-ttu-id="04c3e-109">Diese Kette wartet darauf, dass die aufgerufene Kette zurückkehrt, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="04c3e-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="04c3e-110">Die aufgerufene Kette kann sich in einem anderen Thread befinden, wenn Thread übergreifende Marshalling aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="04c3e-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04c3e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="04c3e-111">Requirements</span></span>  
 <span data-ttu-id="04c3e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04c3e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04c3e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04c3e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04c3e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04c3e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04c3e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04c3e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
