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
ms.openlocfilehash: dc556dfb59e999ed9b7fc5f35c603dc26c35f314
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378708"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="84d6a-102">ICorDebugThread3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84d6a-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="84d6a-103">Stellt den Einstiegspunkt für [ICorDebugStackWalk](icordebugstackwalk-interface.md) und die entsprechenden Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="84d6a-103">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84d6a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="84d6a-104">Methods</span></span>  
  
|<span data-ttu-id="84d6a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="84d6a-105">Method</span></span>|<span data-ttu-id="84d6a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84d6a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84d6a-107">CreateStackWalk-Methode</span><span class="sxs-lookup"><span data-stu-id="84d6a-107">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="84d6a-108">Erstellt ein [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekt für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="84d6a-108">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="84d6a-109">GetActiveInternalFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="84d6a-109">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="84d6a-110">Gibt ein Array interner Frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) -Objekte) auf dem Stapel zurück.</span><span class="sxs-lookup"><span data-stu-id="84d6a-110">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84d6a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84d6a-111">Remarks</span></span>  
 <span data-ttu-id="84d6a-112">`ICorDebugThread3`ist eine logische Erweiterung der ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="84d6a-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84d6a-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="84d6a-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84d6a-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="84d6a-114">Requirements</span></span>  
 <span data-ttu-id="84d6a-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84d6a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84d6a-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84d6a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84d6a-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84d6a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84d6a-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84d6a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d6a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84d6a-119">See also</span></span>

- [<span data-ttu-id="84d6a-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="84d6a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="84d6a-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="84d6a-121">Debugging</span></span>](index.md)
