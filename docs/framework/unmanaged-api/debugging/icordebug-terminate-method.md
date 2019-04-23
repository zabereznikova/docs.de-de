---
title: ICorDebug::Terminate-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 321298ce942b35d11a861c87cdf6b8714179ea97
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080837"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="d5e0e-102">ICorDebug::Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="d5e0e-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="d5e0e-103">Beendet die `ICorDebug` Objekt.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5e0e-104">`Terminate` sollte nicht aufgerufen werden, bis ein [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) Rückruf für alle im Debugmodus befindlichen Prozesse empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e0e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5e0e-105">Syntax</span></span>  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d5e0e-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5e0e-106">Remarks</span></span>  
 <span data-ttu-id="d5e0e-107">`Terminate` muss aufgerufen werden, wenn die `ICorDebug` Objekt ist nicht mehr benötigt.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5e0e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5e0e-108">Requirements</span></span>  
 <span data-ttu-id="d5e0e-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5e0e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5e0e-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5e0e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5e0e-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5e0e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5e0e-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5e0e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e0e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5e0e-113">See also</span></span>

- [<span data-ttu-id="d5e0e-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5e0e-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
