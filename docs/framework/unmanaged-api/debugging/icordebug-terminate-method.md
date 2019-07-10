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
ms.openlocfilehash: 3037fc704ffc3aac4d050cef7857261f138f7d35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738071"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="8f842-102">ICorDebug::Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="8f842-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="8f842-103">Beendet die `ICorDebug` Objekt.</span><span class="sxs-lookup"><span data-stu-id="8f842-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f842-104">`Terminate` sollte nicht aufgerufen werden, bis ein [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) Rückruf für alle im Debugmodus befindlichen Prozesse empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="8f842-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f842-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f842-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8f842-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f842-106">Remarks</span></span>  
 <span data-ttu-id="8f842-107">`Terminate` muss aufgerufen werden, wenn die `ICorDebug` Objekt ist nicht mehr benötigt.</span><span class="sxs-lookup"><span data-stu-id="8f842-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f842-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f842-108">Requirements</span></span>  
 <span data-ttu-id="8f842-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f842-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f842-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f842-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f842-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f842-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f842-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f842-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f842-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f842-113">See also</span></span>

- [<span data-ttu-id="8f842-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f842-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
