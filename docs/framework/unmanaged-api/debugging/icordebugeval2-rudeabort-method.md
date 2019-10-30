---
title: ICorDebugEval2::RudeAbort-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
ms.openlocfilehash: a486935d5d53a6fc7d862160ed1186c5774814c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084799"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="2c3d1-102">ICorDebugEval2::RudeAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="2c3d1-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="2c3d1-103">Bricht die Berechnung ab, die von diesem `ICorDebugEval2` gerade durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2c3d1-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c3d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c3d1-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2c3d1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c3d1-105">Remarks</span></span>  
 <span data-ttu-id="2c3d1-106">`RudeAbort` gibt keine Sperren frei, die der Auswertung enthält, sodass die Debugsitzung in einem unsicheren Zustand bleibt.</span><span class="sxs-lookup"><span data-stu-id="2c3d1-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="2c3d1-107">Diese Methode wird mit äußerster Vorsicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2c3d1-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c3d1-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c3d1-108">Requirements</span></span>  
 <span data-ttu-id="2c3d1-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c3d1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c3d1-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c3d1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c3d1-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c3d1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c3d1-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c3d1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
