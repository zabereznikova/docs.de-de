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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cad8b305de580ce7cf4876939b95cc05d0fd11f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411482"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="43cf9-102">ICorDebugController::Detach-Methode</span><span class="sxs-lookup"><span data-stu-id="43cf9-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="43cf9-103">Trennt den Debugger aus der Domäne verarbeiten oder in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="43cf9-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43cf9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43cf9-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="43cf9-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43cf9-105">Remarks</span></span>  
 <span data-ttu-id="43cf9-106">Die Domäne verarbeiten oder diese Anwendung wird die Ausführung in der Regel wird fortgesetzt, aber das Objekt "ICorDebugProcess" oder "ICorDebugAppDomain" ist nicht mehr gültig, und keine weiteren Rückrufe treten auf.</span><span class="sxs-lookup"><span data-stu-id="43cf9-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="43cf9-107">Wenn ein nicht verwaltetes Debuggen aktiviert ist, wird diese Methode in .NET Framework, Version 2.0 aufgrund von Beschränkungen im Betriebssystem fehl.</span><span class="sxs-lookup"><span data-stu-id="43cf9-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43cf9-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43cf9-108">Requirements</span></span>  
 <span data-ttu-id="43cf9-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43cf9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43cf9-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43cf9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43cf9-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43cf9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43cf9-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43cf9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43cf9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43cf9-113">See Also</span></span>  
 
