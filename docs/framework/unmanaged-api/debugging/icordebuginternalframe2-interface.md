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
ms.openlocfilehash: 2cf75de6a71cfbe25cbde281f837060b88e93753
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087234"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="704c7-102">ICorDebugInternalFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="704c7-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="704c7-103">Enthält Informationen zu internen Frames, u. a. Stapeladresse und Position in Bezug auf ICorDebugFrame-Objekte.</span><span class="sxs-lookup"><span data-stu-id="704c7-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="704c7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="704c7-104">Methods</span></span>  
  
|<span data-ttu-id="704c7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="704c7-105">Method</span></span>|<span data-ttu-id="704c7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="704c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="704c7-107">GetFrameAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="704c7-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="704c7-108">Gibt die Stack-Adresse des internen Frames zurück.</span><span class="sxs-lookup"><span data-stu-id="704c7-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="704c7-109">IsCloserToLeaf-Methode</span><span class="sxs-lookup"><span data-stu-id="704c7-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="704c7-110">Überprüft, ob die `this` Interner Rahmen ist näher an der Blattebene als das angegebene ICorDebugFrame-Objekt.</span><span class="sxs-lookup"><span data-stu-id="704c7-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="704c7-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="704c7-111">Remarks</span></span>  
 <span data-ttu-id="704c7-112">Diese Schnittstelle erweitert die ICorDebugInternalFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="704c7-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="704c7-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="704c7-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="704c7-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="704c7-114">Requirements</span></span>  
 <span data-ttu-id="704c7-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="704c7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="704c7-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="704c7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="704c7-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="704c7-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="704c7-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="704c7-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="704c7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="704c7-119">See also</span></span>

- [<span data-ttu-id="704c7-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="704c7-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="704c7-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="704c7-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
