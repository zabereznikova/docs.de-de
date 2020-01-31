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
ms.openlocfilehash: 19bd869aec7e4d046890d2314f5142753ba0b112
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791391"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="70057-102">ICorDebugThread3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70057-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="70057-103">Stellt den Einstiegspunkt für [ICorDebugStackWalk](icordebugstackwalk-interface.md) und die entsprechenden Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="70057-103">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70057-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="70057-104">Methods</span></span>  
  
|<span data-ttu-id="70057-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="70057-105">Method</span></span>|<span data-ttu-id="70057-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70057-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70057-107">CreateStackWalk-Methode</span><span class="sxs-lookup"><span data-stu-id="70057-107">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="70057-108">Erstellt ein [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekt für den Thread, dessen Stapel entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="70057-108">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="70057-109">GetActiveInternalFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="70057-109">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="70057-110">Gibt ein Array interner Frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) -Objekte) auf dem Stapel zurück.</span><span class="sxs-lookup"><span data-stu-id="70057-110">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70057-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70057-111">Remarks</span></span>  
 <span data-ttu-id="70057-112">`ICorDebugThread3` ist eine logische Erweiterung der ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="70057-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70057-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="70057-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70057-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70057-114">Requirements</span></span>  
 <span data-ttu-id="70057-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70057-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70057-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70057-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70057-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70057-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70057-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70057-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70057-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70057-119">See also</span></span>

- [<span data-ttu-id="70057-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="70057-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="70057-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="70057-121">Debugging</span></span>](index.md)
