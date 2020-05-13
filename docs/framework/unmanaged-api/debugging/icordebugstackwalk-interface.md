---
title: ICorDebugStackWalk-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: 5f71dfcdffaaa683ca4f2abebaa99115ef90e0ff
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378903"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="716b1-102">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="716b1-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="716b1-103">Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.</span><span class="sxs-lookup"><span data-stu-id="716b1-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="716b1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="716b1-104">Methods</span></span>  
  
|<span data-ttu-id="716b1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="716b1-105">Method</span></span>|<span data-ttu-id="716b1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="716b1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="716b1-107">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="716b1-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="716b1-108">Gibt den Kontext für den aktuellen Frame im- `ICorDebugStackWalk` Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="716b1-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="716b1-109">SetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="716b1-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="716b1-110">Legt den `ICorDebugStackWalk` aktuellen Kontext des Objekts auf einen gültigen Kontext für den Thread fest.</span><span class="sxs-lookup"><span data-stu-id="716b1-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="716b1-111">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="716b1-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="716b1-112">Verschiebt das- `ICorDebugStackWalk` Objekt in den nächsten Frame.</span><span class="sxs-lookup"><span data-stu-id="716b1-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="716b1-113">GetFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="716b1-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="716b1-114">Ruft den aktuellen Frame im- `ICorDebugStackWalk` Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="716b1-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="716b1-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="716b1-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="716b1-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="716b1-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="716b1-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="716b1-117">Requirements</span></span>  
 <span data-ttu-id="716b1-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="716b1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="716b1-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="716b1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="716b1-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="716b1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="716b1-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="716b1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716b1-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="716b1-122">See also</span></span>

- [<span data-ttu-id="716b1-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="716b1-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="716b1-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="716b1-124">Debugging</span></span>](index.md)
