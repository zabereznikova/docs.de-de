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
ms.openlocfilehash: 85a9bde77f7c393756ec1d3e7d30b96392aa6a94
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151800"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="ba3c1-102">ICorDebugController::Detach-Methode</span><span class="sxs-lookup"><span data-stu-id="ba3c1-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="ba3c1-103">Trennt den Debugger aus der Domäne Prozess- oder Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ba3c1-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba3c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba3c1-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ba3c1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba3c1-105">Remarks</span></span>  
 <span data-ttu-id="ba3c1-106">Der Prozess oder eine Anwendung weiterhin ordnungsgemäß, aber das "ICorDebugProcess" oder "ICorDebugAppDomain"-Objekt ist nicht mehr gültig und keine weiteren Rückrufe ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ba3c1-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="ba3c1-107">Wenn nicht verwaltetes debugging aktiviert ist, wird diese Methode in .NET Framework, Version 2.0 aufgrund von Beschränkungen im Betriebssystem fehl.</span><span class="sxs-lookup"><span data-stu-id="ba3c1-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba3c1-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ba3c1-108">Requirements</span></span>  
 <span data-ttu-id="ba3c1-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba3c1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba3c1-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba3c1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba3c1-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba3c1-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ba3c1-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ba3c1-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ba3c1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba3c1-113">See also</span></span>
