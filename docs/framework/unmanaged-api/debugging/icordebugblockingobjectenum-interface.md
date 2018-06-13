---
title: ICorDebugBlockingObjectEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f22d9d86e2b943a8825e1ec271a401b03f73fb6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407013"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="fcb73-102">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcb73-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="fcb73-103">Stellt einen Enumerator bereit, eine Liste der [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="fcb73-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="fcb73-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fcb73-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fcb73-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fcb73-105">Methods</span></span>  
  
|<span data-ttu-id="fcb73-106">Methode</span><span class="sxs-lookup"><span data-stu-id="fcb73-106">Method</span></span>|<span data-ttu-id="fcb73-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcb73-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fcb73-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="fcb73-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="fcb73-109">Durchläuft eine Liste von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="fcb73-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcb73-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcb73-110">Remarks</span></span>  
 <span data-ttu-id="fcb73-111">Jede `CorDebugBlockingObject`-Struktur stellt ein Objekt dar, das einen Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="fcb73-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcb73-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fcb73-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcb73-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fcb73-113">Requirements</span></span>  
 <span data-ttu-id="fcb73-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcb73-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcb73-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcb73-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcb73-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcb73-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcb73-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcb73-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb73-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcb73-118">See Also</span></span>  
 [<span data-ttu-id="fcb73-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fcb73-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fcb73-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fcb73-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
