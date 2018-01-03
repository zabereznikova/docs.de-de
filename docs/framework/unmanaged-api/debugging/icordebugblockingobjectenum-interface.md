---
title: ICorDebugBlockingObjectEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBlockingObjectEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBlockingObjectEnum
helpviewer_keywords: ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d35d4ee2ce3c1b7b0f54d78dba8b8639c522d509
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="639b3-102">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="639b3-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="639b3-103">Stellt einen Enumerator bereit, eine Liste der [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="639b3-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="639b3-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="639b3-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="639b3-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="639b3-105">Methods</span></span>  
  
|<span data-ttu-id="639b3-106">Methode</span><span class="sxs-lookup"><span data-stu-id="639b3-106">Method</span></span>|<span data-ttu-id="639b3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="639b3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="639b3-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="639b3-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="639b3-109">Durchläuft eine Liste von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="639b3-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="639b3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="639b3-110">Remarks</span></span>  
 <span data-ttu-id="639b3-111">Jede `CorDebugBlockingObject`-Struktur stellt ein Objekt dar, das einen Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="639b3-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="639b3-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="639b3-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="639b3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="639b3-113">Requirements</span></span>  
 <span data-ttu-id="639b3-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="639b3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="639b3-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="639b3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="639b3-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="639b3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="639b3-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="639b3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639b3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="639b3-118">See Also</span></span>  
 [<span data-ttu-id="639b3-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="639b3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="639b3-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="639b3-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
