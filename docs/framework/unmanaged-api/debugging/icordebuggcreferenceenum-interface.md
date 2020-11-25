---
title: ICorDebugGCReferenceEnum-Schnittstelle
ms.date: 03/30/2017
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
ms.openlocfilehash: 12ce800cb83ef4f79710aa441b50be860526023c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728120"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="1950f-102">ICorDebugGCReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1950f-102">ICorDebugGCReferenceEnum Interface</span></span>

<span data-ttu-id="1950f-103">Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1950f-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1950f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1950f-104">Methods</span></span>  
  
|<span data-ttu-id="1950f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1950f-105">Method</span></span>|<span data-ttu-id="1950f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1950f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1950f-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="1950f-107">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="1950f-108">Ruft die angegebene Anzahl von [COR_GC_REFERENCE](cor-gc-reference-structure.md) Instanzen ab, die Informationen über Objekte enthalten, für die eine Garbage Collection durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1950f-108">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1950f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1950f-109">Remarks</span></span>  

 <span data-ttu-id="1950f-110">Die `ICorDebugGCReferenceEnum` Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1950f-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="1950f-111">Eine `ICorDebugGCReferenceEnum` Instanz wird durch Aufrufen der [ICorDebugProcess5:: enumerategcreferences](icordebugprocess5-enumerategcreferences-method.md) -Methode mit [COR_GC_REFERENCE](cor-gc-reference-structure.md) Instanzen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="1950f-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="1950f-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) Objekte können durch Aufrufen der [icordebuggcreferen:: Next](icordebuggcreferenceenum-next-method.md) -Methode aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="1950f-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="1950f-113">Die [COR_GC_REFERENCE](cor-gc-reference-structure.md) Objekte in der Auflistung, die von dieser Methode aufgefüllt werden, stellen drei Arten von Objekten dar:</span><span class="sxs-lookup"><span data-stu-id="1950f-113">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="1950f-114">Objekte aus allen verwalteten stapeln.</span><span class="sxs-lookup"><span data-stu-id="1950f-114">Objects from all managed stacks.</span></span> <span data-ttu-id="1950f-115">Dies schließt sowohl Live Verweise in verwaltetem Code als auch Objekte ein, die vom Common Language Runtime erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1950f-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="1950f-116">Objekte aus der Handle-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1950f-116">Objects from the handle table.</span></span> <span data-ttu-id="1950f-117">Dies schließt starke Verweise ( `HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT` ) sowie statische Variablen in einem Modul ein.</span><span class="sxs-lookup"><span data-stu-id="1950f-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="1950f-118">Objekte aus der Finalizerwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="1950f-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="1950f-119">Die Finalizer-Warteschlange wurzelt Objekte, bis der Finalizer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1950f-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1950f-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1950f-120">Requirements</span></span>  

 <span data-ttu-id="1950f-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1950f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1950f-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1950f-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1950f-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1950f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1950f-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1950f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1950f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1950f-125">See also</span></span>

- [<span data-ttu-id="1950f-126">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1950f-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
