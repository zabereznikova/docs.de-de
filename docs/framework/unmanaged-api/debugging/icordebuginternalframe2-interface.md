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
ms.openlocfilehash: dd867db8886c1c74d209e080b6b810ed4adc3654
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589333"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="afaa6-102">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="afaa6-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="afaa6-103">Enthält Informationen zu internen Frames, u. a. Stapeladresse und Position in Bezug auf ICorDebugFrame-Objekte.</span><span class="sxs-lookup"><span data-stu-id="afaa6-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="afaa6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="afaa6-104">Methods</span></span>  
  
|<span data-ttu-id="afaa6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="afaa6-105">Method</span></span>|<span data-ttu-id="afaa6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afaa6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="afaa6-107">GetFrameAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="afaa6-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="afaa6-108">Gibt die Stack-Adresse des internen Frames zurück.</span><span class="sxs-lookup"><span data-stu-id="afaa6-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="afaa6-109">IsCloserToLeaf-Methode</span><span class="sxs-lookup"><span data-stu-id="afaa6-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="afaa6-110">Überprüft, ob die `this` Interner Rahmen ist näher an der Blattebene als das angegebene ICorDebugFrame-Objekt.</span><span class="sxs-lookup"><span data-stu-id="afaa6-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afaa6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="afaa6-111">Remarks</span></span>  
 <span data-ttu-id="afaa6-112">Diese Schnittstelle erweitert die ICorDebugInternalFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="afaa6-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afaa6-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="afaa6-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afaa6-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="afaa6-114">Requirements</span></span>  
 <span data-ttu-id="afaa6-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afaa6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afaa6-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afaa6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afaa6-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afaa6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afaa6-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afaa6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afaa6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afaa6-119">See also</span></span>
- [<span data-ttu-id="afaa6-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="afaa6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="afaa6-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="afaa6-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
