---
title: ICorDebugThread3-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3
helpviewer_keywords: ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed505cacc5286d27bc9a94eaa192dc6b889eb525
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="96f56-102">ICorDebugThread3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96f56-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="96f56-103">Stellt den Einstiegspunkt für die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) und entsprechende Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="96f56-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96f56-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="96f56-104">Methods</span></span>  
  
|<span data-ttu-id="96f56-105">Methode</span><span class="sxs-lookup"><span data-stu-id="96f56-105">Method</span></span>|<span data-ttu-id="96f56-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96f56-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96f56-107">CreateStackWalk-Methode</span><span class="sxs-lookup"><span data-stu-id="96f56-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="96f56-108">Erstellt ein [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="96f56-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="96f56-109">GetActiveInternalFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="96f56-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="96f56-110">Gibt ein Array von internen Frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) Objekte) auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="96f56-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96f56-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96f56-111">Remarks</span></span>  
 <span data-ttu-id="96f56-112">`ICorDebugThread3`ist eine logische Erweiterung der ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="96f56-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96f56-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="96f56-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96f56-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96f56-114">Requirements</span></span>  
 <span data-ttu-id="96f56-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96f56-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96f56-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96f56-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96f56-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96f56-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96f56-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96f56-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96f56-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96f56-119">See Also</span></span>  
 [<span data-ttu-id="96f56-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="96f56-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="96f56-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="96f56-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
