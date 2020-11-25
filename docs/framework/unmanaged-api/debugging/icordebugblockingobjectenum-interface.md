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
ms.openlocfilehash: 221acf9bea714728a81b9f15c8165c1f9eba16a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719202"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="78b30-102">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78b30-102">ICorDebugBlockingObjectEnum Interface</span></span>

<span data-ttu-id="78b30-103">Stellt einen Enumerator für eine Liste von [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Strukturen bereit.</span><span class="sxs-lookup"><span data-stu-id="78b30-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="78b30-104">Diese Schnittstelle ist eine Unterklasse von der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="78b30-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="78b30-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="78b30-105">Methods</span></span>  
  
|<span data-ttu-id="78b30-106">Methode</span><span class="sxs-lookup"><span data-stu-id="78b30-106">Method</span></span>|<span data-ttu-id="78b30-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="78b30-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="78b30-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="78b30-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="78b30-109">Listet die [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Strukturen auf.</span><span class="sxs-lookup"><span data-stu-id="78b30-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78b30-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="78b30-110">Remarks</span></span>  

 <span data-ttu-id="78b30-111">Jede `CorDebugBlockingObject`-Struktur stellt ein Objekt dar, das einen Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="78b30-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78b30-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="78b30-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78b30-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="78b30-113">Requirements</span></span>  

 <span data-ttu-id="78b30-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78b30-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78b30-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78b30-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78b30-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78b30-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78b30-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78b30-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b30-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78b30-118">See also</span></span>

- [<span data-ttu-id="78b30-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="78b30-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="78b30-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="78b30-120">Debugging</span></span>](index.md)
