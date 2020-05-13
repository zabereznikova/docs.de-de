---
title: ICorDebugInternalFrame2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
ms.openlocfilehash: ce3ca4745727a1738fdc1a526480d70ffc55ccf8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209902"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="e14c2-102">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e14c2-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="e14c2-103">Stellt Informationen zu internen Frames bereit, u. a. Stapeladresse und Position in Bezug auf ICorDebugFrame-Objekte.</span><span class="sxs-lookup"><span data-stu-id="e14c2-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e14c2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e14c2-104">Methods</span></span>  
  
|<span data-ttu-id="e14c2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e14c2-105">Method</span></span>|<span data-ttu-id="e14c2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e14c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e14c2-107">GetFrameAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="e14c2-107">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="e14c2-108">Gibt die Stapel Adresse des internen Frames zurück.</span><span class="sxs-lookup"><span data-stu-id="e14c2-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="e14c2-109">IsCloserToLeaf-Methode</span><span class="sxs-lookup"><span data-stu-id="e14c2-109">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="e14c2-110">Überprüft, ob sich der `this` interne Frame näher an dem Blatt als das angegebene ICorDebugFrame-Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="e14c2-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e14c2-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e14c2-111">Remarks</span></span>  
 <span data-ttu-id="e14c2-112">Diese Schnittstelle erweitert die ICorDebug-internalframe-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e14c2-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e14c2-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e14c2-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e14c2-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e14c2-114">Requirements</span></span>  
 <span data-ttu-id="e14c2-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e14c2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e14c2-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e14c2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e14c2-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e14c2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e14c2-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e14c2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e14c2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e14c2-119">See also</span></span>

- [<span data-ttu-id="e14c2-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e14c2-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e14c2-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e14c2-121">Debugging</span></span>](index.md)
