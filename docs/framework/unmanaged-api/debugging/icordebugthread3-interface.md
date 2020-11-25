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
ms.openlocfilehash: 015d0061e5be5bbc212243ca06f1d165abe4496a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729303"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="d45b5-102">ICorDebugThread3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d45b5-102">ICorDebugThread3 Interface</span></span>

<span data-ttu-id="d45b5-103">Stellt den Einstiegspunkt für [ICorDebugStackWalk](icordebugstackwalk-interface.md) und die entsprechenden Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="d45b5-103">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d45b5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d45b5-104">Methods</span></span>  
  
|<span data-ttu-id="d45b5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d45b5-105">Method</span></span>|<span data-ttu-id="d45b5-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d45b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d45b5-107">CreateStackWalk-Methode</span><span class="sxs-lookup"><span data-stu-id="d45b5-107">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="d45b5-108">Erstellt ein [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekt für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d45b5-108">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="d45b5-109">GetActiveInternalFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="d45b5-109">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="d45b5-110">Gibt ein Array interner Frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) -Objekte) auf dem Stapel zurück.</span><span class="sxs-lookup"><span data-stu-id="d45b5-110">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d45b5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d45b5-111">Remarks</span></span>  

 <span data-ttu-id="d45b5-112">`ICorDebugThread3` ist eine logische Erweiterung der ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d45b5-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d45b5-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d45b5-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d45b5-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d45b5-114">Requirements</span></span>  

 <span data-ttu-id="d45b5-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d45b5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d45b5-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d45b5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d45b5-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d45b5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d45b5-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d45b5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d45b5-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d45b5-119">See also</span></span>

- [<span data-ttu-id="d45b5-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d45b5-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d45b5-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d45b5-121">Debugging</span></span>](index.md)
