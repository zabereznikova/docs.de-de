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
ms.openlocfilehash: be1e1cd0d38ad71de43478af5565bb1ac98a8c0d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778004"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="b7d10-102">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b7d10-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="b7d10-103">Stellt einen Enumerator für eine Liste von [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Strukturen bereit.</span><span class="sxs-lookup"><span data-stu-id="b7d10-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="b7d10-104">Diese Schnittstelle ist eine Unterklasse von der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b7d10-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7d10-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b7d10-105">Methods</span></span>  
  
|<span data-ttu-id="b7d10-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="b7d10-106">Method</span></span>|<span data-ttu-id="b7d10-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7d10-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7d10-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="b7d10-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="b7d10-109">Listet die [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Strukturen auf.</span><span class="sxs-lookup"><span data-stu-id="b7d10-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d10-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7d10-110">Remarks</span></span>  
 <span data-ttu-id="b7d10-111">Jede `CorDebugBlockingObject`-Struktur stellt ein Objekt dar, das einen Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="b7d10-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7d10-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b7d10-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7d10-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7d10-113">Requirements</span></span>  
 <span data-ttu-id="b7d10-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7d10-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d10-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7d10-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7d10-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7d10-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7d10-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7d10-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d10-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7d10-118">See also</span></span>

- [<span data-ttu-id="b7d10-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b7d10-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b7d10-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b7d10-120">Debugging</span></span>](index.md)
