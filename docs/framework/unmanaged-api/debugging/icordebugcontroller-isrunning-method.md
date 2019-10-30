---
title: ICorDebugController::IsRunning-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.IsRunning
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type:
- apiref
ms.openlocfilehash: f24c07a654dc2345cb65226463573576a6fb3658
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125338"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="15e22-102">ICorDebugController::IsRunning-Methode</span><span class="sxs-lookup"><span data-stu-id="15e22-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="15e22-103">Ruft einen Wert ab, der angibt, ob die Threads im Prozess momentan frei ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="15e22-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15e22-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15e22-104">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15e22-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15e22-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="15e22-106">vorgenommen Ein Zeiger auf einen Wert, der `true` wird, wenn die Threads im Prozess frei ausgeführt werden. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="15e22-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15e22-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15e22-107">Requirements</span></span>  
 <span data-ttu-id="15e22-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15e22-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15e22-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15e22-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15e22-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15e22-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15e22-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15e22-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e22-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15e22-112">See also</span></span>
