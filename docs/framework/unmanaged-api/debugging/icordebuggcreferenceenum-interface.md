---
title: ICorDebugGCReferenceEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1afe52c3df8f61b234b3c68ee819ba8389593c82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="10854-102">ICorDebugGCReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10854-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="10854-103">Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="10854-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10854-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="10854-104">Methods</span></span>  
  
|<span data-ttu-id="10854-105">Methode</span><span class="sxs-lookup"><span data-stu-id="10854-105">Method</span></span>|<span data-ttu-id="10854-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10854-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10854-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="10854-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="10854-108">Ruft die angegebene Anzahl von [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Instanzen, die Informationen zu Objekten enthalten, die Garbage Collection übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="10854-108">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10854-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10854-109">Remarks</span></span>  
 <span data-ttu-id="10854-110">Die `ICorDebugGCReferenceEnum` Schnittstelle implementiert, die "ICorDebugEnum"-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="10854-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="10854-111">Ein `ICorDebugGCReferenceEnum` Instanz wird mit aufgefüllt [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Instanzen durch Aufrufen der [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="10854-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="10854-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Objekte aufgelistet werden können, durch Aufrufen der [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="10854-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="10854-113">Die [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Objekte in der Auflistung, die von dieser Methode aufgefüllt darstellen drei Arten von Objekten:</span><span class="sxs-lookup"><span data-stu-id="10854-113">The [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
-   <span data-ttu-id="10854-114">Objekte aus allen verwalteten Stapel.</span><span class="sxs-lookup"><span data-stu-id="10854-114">Objects from all managed stacks.</span></span> <span data-ttu-id="10854-115">Dies schließt die aktive Verweise in verwaltetem Code als auch Objekte, die von der common Language Runtime erstellt.</span><span class="sxs-lookup"><span data-stu-id="10854-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="10854-116">Objekte aus der Handletabelle.</span><span class="sxs-lookup"><span data-stu-id="10854-116">Objects from the handle table.</span></span> <span data-ttu-id="10854-117">Dies schließt starken Verweise (`HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT`) und statische Variablen in einem Modul.</span><span class="sxs-lookup"><span data-stu-id="10854-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="10854-118">Objekte aus der Finalizerwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="10854-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="10854-119">Die Finalizer-Warteschlange Stämme Objekte auf, bis der Finalizer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="10854-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10854-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10854-120">Requirements</span></span>  
 <span data-ttu-id="10854-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10854-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10854-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10854-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10854-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10854-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10854-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10854-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10854-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10854-125">See Also</span></span>  
 [<span data-ttu-id="10854-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="10854-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
