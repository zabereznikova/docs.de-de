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
ms.openlocfilehash: 4f2dae147f8667a73036dbcf873e2082996b2755
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666984"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="ad0c0-102">ICorDebugController::Detach-Methode</span><span class="sxs-lookup"><span data-stu-id="ad0c0-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="ad0c0-103">Trennt den Debugger aus der Domäne Prozess- oder Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ad0c0-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad0c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad0c0-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ad0c0-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad0c0-105">Remarks</span></span>  
 <span data-ttu-id="ad0c0-106">Der Prozess oder eine Anwendung weiterhin ordnungsgemäß, aber das "ICorDebugProcess" oder "ICorDebugAppDomain"-Objekt ist nicht mehr gültig und keine weiteren Rückrufe ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ad0c0-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="ad0c0-107">Wenn nicht verwaltetes debugging aktiviert ist, wird diese Methode in .NET Framework, Version 2.0 aufgrund von Beschränkungen im Betriebssystem fehl.</span><span class="sxs-lookup"><span data-stu-id="ad0c0-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad0c0-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad0c0-108">Requirements</span></span>  
 <span data-ttu-id="ad0c0-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad0c0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad0c0-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad0c0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad0c0-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad0c0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad0c0-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad0c0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad0c0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad0c0-113">See also</span></span>

