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
ms.openlocfilehash: 5a23d21d0ed8c6a6a226d5e58eafb7bde65a4896
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645434"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="2ce81-102">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ce81-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="2ce81-103">Stellt einen Enumerator bereit, eine Liste der [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="2ce81-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="2ce81-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2ce81-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ce81-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2ce81-105">Methods</span></span>  
  
|<span data-ttu-id="2ce81-106">Methode</span><span class="sxs-lookup"><span data-stu-id="2ce81-106">Method</span></span>|<span data-ttu-id="2ce81-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ce81-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ce81-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="2ce81-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="2ce81-109">Durchläuft eine Liste von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="2ce81-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ce81-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ce81-110">Remarks</span></span>  
 <span data-ttu-id="2ce81-111">Jede `CorDebugBlockingObject`-Struktur stellt ein Objekt dar, das einen Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="2ce81-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ce81-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2ce81-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ce81-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ce81-113">Requirements</span></span>  
 <span data-ttu-id="2ce81-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ce81-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ce81-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ce81-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ce81-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ce81-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ce81-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ce81-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce81-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ce81-118">See also</span></span>

- [<span data-ttu-id="2ce81-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2ce81-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2ce81-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2ce81-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
