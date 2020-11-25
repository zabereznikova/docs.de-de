---
title: ICorDebugController::Detach-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
ms.openlocfilehash: 55acb6e3ec60925cba3d8aa5328547c54f270356
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732670"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="b1de0-102">ICorDebugController::Detach-Methode</span><span class="sxs-lookup"><span data-stu-id="b1de0-102">ICorDebugController::Detach Method</span></span>

<span data-ttu-id="b1de0-103">Trennt den Debugger vom Prozess oder der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="b1de0-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1de0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1de0-104">Syntax</span></span>  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b1de0-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1de0-105">Remarks</span></span>  

 <span data-ttu-id="b1de0-106">Der Prozess oder die Anwendungsdomäne wird normal ausgeführt, aber das Objekt "ICorDebugProcess" oder "ICorDebugAppDomain" ist nicht mehr gültig, und es werden keine weiteren Rückrufe mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1de0-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="b1de0-107">Wenn in der .NET Framework Version 2,0 die Option nicht verwaltetes Debuggen aktiviert ist, tritt bei dieser Methode ein Fehler aufgrund von Einschränkungen des Betriebssystems auf.</span><span class="sxs-lookup"><span data-stu-id="b1de0-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1de0-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b1de0-108">Requirements</span></span>  

 <span data-ttu-id="b1de0-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1de0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1de0-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1de0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1de0-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1de0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1de0-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1de0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1de0-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1de0-113">See also</span></span>
