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
ms.openlocfilehash: 91e4967d6820f8f059262e7a18add072332c509d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532784"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="3fa24-102">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3fa24-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="3fa24-103">Stellt einen Enumerator bereit, eine Liste der [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="3fa24-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="3fa24-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3fa24-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3fa24-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3fa24-105">Methods</span></span>  
  
|<span data-ttu-id="3fa24-106">Methode</span><span class="sxs-lookup"><span data-stu-id="3fa24-106">Method</span></span>|<span data-ttu-id="3fa24-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3fa24-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3fa24-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="3fa24-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="3fa24-109">Durchläuft eine Liste von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="3fa24-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fa24-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fa24-110">Remarks</span></span>  
 <span data-ttu-id="3fa24-111">Jede `CorDebugBlockingObject`-Struktur stellt ein Objekt dar, das einen Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="3fa24-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fa24-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3fa24-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fa24-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3fa24-113">Requirements</span></span>  
 <span data-ttu-id="3fa24-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fa24-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fa24-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fa24-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fa24-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fa24-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fa24-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fa24-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa24-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fa24-118">See also</span></span>
- [<span data-ttu-id="3fa24-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3fa24-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3fa24-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="3fa24-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
