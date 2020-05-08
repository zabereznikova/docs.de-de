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
ms.openlocfilehash: 8be4332da77c3fbf4229a3fbeb9ba835a7a13eee
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894795"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="5d1b4-102">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d1b4-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="5d1b4-103">Stellt einen Enumerator für eine Liste von [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Strukturen bereit.</span><span class="sxs-lookup"><span data-stu-id="5d1b4-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="5d1b4-104">Diese Schnittstelle ist eine Unterklasse von der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5d1b4-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d1b4-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="5d1b4-105">Methods</span></span>  
  
|<span data-ttu-id="5d1b4-106">Methode</span><span class="sxs-lookup"><span data-stu-id="5d1b4-106">Method</span></span>|<span data-ttu-id="5d1b4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d1b4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d1b4-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="5d1b4-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="5d1b4-109">Listet die [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Strukturen auf.</span><span class="sxs-lookup"><span data-stu-id="5d1b4-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d1b4-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d1b4-110">Remarks</span></span>  
 <span data-ttu-id="5d1b4-111">Jede `CorDebugBlockingObject`-Struktur stellt ein Objekt dar, das einen Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="5d1b4-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d1b4-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5d1b4-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d1b4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d1b4-113">Requirements</span></span>  
 <span data-ttu-id="5d1b4-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d1b4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d1b4-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d1b4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d1b4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d1b4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d1b4-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d1b4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d1b4-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d1b4-118">See also</span></span>

- [<span data-ttu-id="5d1b4-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5d1b4-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5d1b4-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5d1b4-120">Debugging</span></span>](index.md)
