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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161459"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="f5e35-102">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5e35-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="f5e35-103">Stellt einen Enumerator bereit, eine Liste der [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="f5e35-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="f5e35-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f5e35-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5e35-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f5e35-105">Methods</span></span>  
  
|<span data-ttu-id="f5e35-106">Methode</span><span class="sxs-lookup"><span data-stu-id="f5e35-106">Method</span></span>|<span data-ttu-id="f5e35-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5e35-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5e35-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="f5e35-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="f5e35-109">Durchläuft eine Liste von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="f5e35-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5e35-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5e35-110">Remarks</span></span>  
 <span data-ttu-id="f5e35-111">Jede `CorDebugBlockingObject`-Struktur stellt ein Objekt dar, das einen Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="f5e35-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5e35-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f5e35-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5e35-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5e35-113">Requirements</span></span>  
 <span data-ttu-id="f5e35-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5e35-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5e35-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5e35-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5e35-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5e35-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f5e35-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f5e35-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5e35-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5e35-118">See also</span></span>

- [<span data-ttu-id="f5e35-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f5e35-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f5e35-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f5e35-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
