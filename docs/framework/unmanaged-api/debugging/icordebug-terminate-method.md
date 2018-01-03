---
title: ICorDebug::Terminate-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.Terminate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e416f8ea20bde49a1c1cdb5d61bc4a6bfbce7913
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="bf443-102">ICorDebug::Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="bf443-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="bf443-103">Beendet die `ICorDebug` Objekt.</span><span class="sxs-lookup"><span data-stu-id="bf443-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf443-104">`Terminate`darf nicht aufgerufen werden, bis ein [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) Rückruf wurde für alle Prozesse gedebuggt wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="bf443-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf443-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf443-105">Syntax</span></span>  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="bf443-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf443-106">Remarks</span></span>  
 <span data-ttu-id="bf443-107">`Terminate`muss aufgerufen werden, wenn die `ICorDebug` Objekt nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf443-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf443-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf443-108">Requirements</span></span>  
 <span data-ttu-id="bf443-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf443-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf443-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf443-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf443-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf443-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf443-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf443-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf443-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf443-113">See Also</span></span>  
 [<span data-ttu-id="bf443-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf443-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
