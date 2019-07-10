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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99dbe5c5da5b8c169e34aa29afca507cc6624f0f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748793"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="120da-102">ICorDebugController::IsRunning-Methode</span><span class="sxs-lookup"><span data-stu-id="120da-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="120da-103">Ruft einen Wert, der angibt, ob die Threads im Prozess frei derzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="120da-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="120da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="120da-104">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="120da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="120da-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="120da-106">[out] Ein Zeiger auf einen Wert `true` , wenn die Threads im Prozess, frei ist, andernfalls ausgeführt werden `false`.</span><span class="sxs-lookup"><span data-stu-id="120da-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="120da-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="120da-107">Requirements</span></span>  
 <span data-ttu-id="120da-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="120da-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="120da-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="120da-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="120da-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="120da-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="120da-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="120da-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120da-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="120da-112">See also</span></span>
