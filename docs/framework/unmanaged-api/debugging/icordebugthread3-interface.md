---
title: ICorDebugThread3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5f4cecda80238e7a53cf2aa2a8219c49c2b3f9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531719"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="b4525-102">ICorDebugThread3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4525-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="b4525-103">Stellt den Einstiegspunkt für die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) und entsprechende Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="b4525-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b4525-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b4525-104">Methods</span></span>  
  
|<span data-ttu-id="b4525-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b4525-105">Method</span></span>|<span data-ttu-id="b4525-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4525-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4525-107">CreateStackWalk-Methode</span><span class="sxs-lookup"><span data-stu-id="b4525-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="b4525-108">Erstellt eine [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) -Objekt für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b4525-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="b4525-109">GetActiveInternalFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="b4525-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="b4525-110">Gibt ein Array von internen Frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) Objekte) auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="b4525-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4525-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4525-111">Remarks</span></span>  
 <span data-ttu-id="b4525-112">`ICorDebugThread3` ist eine logische Erweiterung der ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b4525-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4525-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b4525-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4525-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4525-114">Requirements</span></span>  
 <span data-ttu-id="b4525-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4525-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4525-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4525-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4525-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4525-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4525-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4525-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4525-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4525-119">See also</span></span>
- [<span data-ttu-id="b4525-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b4525-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b4525-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b4525-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
