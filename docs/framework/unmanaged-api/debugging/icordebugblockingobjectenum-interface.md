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
ms.openlocfilehash: bfd61d985eac3ab56d8a5df9474b2b1a9f641f3e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122842"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="7fe91-102">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fe91-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="7fe91-103">Stellt einen Enumerator für eine Liste von [Cordebug-blockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Strukturen bereit.</span><span class="sxs-lookup"><span data-stu-id="7fe91-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="7fe91-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7fe91-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7fe91-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7fe91-105">Methods</span></span>  
  
|<span data-ttu-id="7fe91-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7fe91-106">Method</span></span>|<span data-ttu-id="7fe91-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fe91-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7fe91-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="7fe91-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="7fe91-109">Listet die [Cordebug-blockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Strukturen auf.</span><span class="sxs-lookup"><span data-stu-id="7fe91-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fe91-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7fe91-110">Remarks</span></span>  
 <span data-ttu-id="7fe91-111">Jede `CorDebugBlockingObject`-Struktur stellt ein Objekt dar, das einen Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="7fe91-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fe91-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7fe91-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fe91-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7fe91-113">Requirements</span></span>  
 <span data-ttu-id="7fe91-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fe91-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fe91-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7fe91-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fe91-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fe91-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fe91-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fe91-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fe91-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fe91-118">See also</span></span>

- [<span data-ttu-id="7fe91-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7fe91-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7fe91-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7fe91-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
