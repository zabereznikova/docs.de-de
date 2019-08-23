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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2377773b471b387376f0284522ebe29d6b003ae3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910113"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="c5f8a-102">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5f8a-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="c5f8a-103">Stellt Informationen zu internen Frames bereit, einschließlich Stapel Adresse und Position in Bezug auf ICorDebugFrame-Objekte.</span><span class="sxs-lookup"><span data-stu-id="c5f8a-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5f8a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c5f8a-104">Methods</span></span>  
  
|<span data-ttu-id="c5f8a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c5f8a-105">Method</span></span>|<span data-ttu-id="c5f8a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5f8a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5f8a-107">GetFrameAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="c5f8a-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="c5f8a-108">Gibt die Stapel Adresse des internen Frames zurück.</span><span class="sxs-lookup"><span data-stu-id="c5f8a-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="c5f8a-109">IsCloserToLeaf-Methode</span><span class="sxs-lookup"><span data-stu-id="c5f8a-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="c5f8a-110">Überprüft, ob `this` sich der interne Frame näher an dem Blatt als das angegebene ICorDebugFrame-Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="c5f8a-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5f8a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5f8a-111">Remarks</span></span>  
 <span data-ttu-id="c5f8a-112">Diese Schnittstelle erweitert die ICorDebug-internalframe-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c5f8a-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5f8a-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c5f8a-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5f8a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5f8a-114">Requirements</span></span>  
 <span data-ttu-id="c5f8a-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5f8a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5f8a-116">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="c5f8a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5f8a-117">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5f8a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5f8a-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5f8a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f8a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5f8a-119">See also</span></span>

- [<span data-ttu-id="c5f8a-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c5f8a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c5f8a-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c5f8a-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
