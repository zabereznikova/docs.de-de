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
ms.openlocfilehash: de37bb34aee9b6536ff892ac30855761bcc69445
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963126"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="1070e-102">ICorDebug::Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="1070e-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="1070e-103">Beendet das `ICorDebug` -Objekt.</span><span class="sxs-lookup"><span data-stu-id="1070e-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1070e-104">`Terminate`sollte erst aufgerufen werden, wenn ein [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) -Rückruf für alle Prozesse empfangen wurde, die gedebuggt werden.</span><span class="sxs-lookup"><span data-stu-id="1070e-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1070e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1070e-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1070e-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1070e-106">Remarks</span></span>  
 <span data-ttu-id="1070e-107">`Terminate`muss aufgerufen werden, wenn `ICorDebug` das Objekt nicht mehr benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="1070e-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1070e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1070e-108">Requirements</span></span>  
 <span data-ttu-id="1070e-109">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1070e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1070e-110">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="1070e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1070e-111">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1070e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1070e-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1070e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1070e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1070e-113">See also</span></span>

- [<span data-ttu-id="1070e-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1070e-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
