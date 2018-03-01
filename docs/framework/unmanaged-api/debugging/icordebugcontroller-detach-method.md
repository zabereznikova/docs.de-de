---
title: ICorDebugController::Detach-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59fe2c4bfbd91afd263a0ada1eb355aaa8914aa2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="99231-102">ICorDebugController::Detach-Methode</span><span class="sxs-lookup"><span data-stu-id="99231-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="99231-103">Trennt den Debugger aus der Domäne verarbeiten oder in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="99231-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99231-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99231-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="99231-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99231-105">Remarks</span></span>  
 <span data-ttu-id="99231-106">Die Domäne verarbeiten oder diese Anwendung wird die Ausführung in der Regel wird fortgesetzt, aber das Objekt "ICorDebugProcess" oder "ICorDebugAppDomain" ist nicht mehr gültig, und keine weiteren Rückrufe treten auf.</span><span class="sxs-lookup"><span data-stu-id="99231-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="99231-107">Wenn ein nicht verwaltetes Debuggen aktiviert ist, wird diese Methode in .NET Framework, Version 2.0 aufgrund von Beschränkungen im Betriebssystem fehl.</span><span class="sxs-lookup"><span data-stu-id="99231-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99231-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99231-108">Requirements</span></span>  
 <span data-ttu-id="99231-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99231-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99231-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99231-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99231-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99231-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99231-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99231-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99231-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99231-113">See Also</span></span>  
 
