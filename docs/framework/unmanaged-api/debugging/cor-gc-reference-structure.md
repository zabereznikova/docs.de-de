---
title: COR_GC_REFERENCE-Struktur
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179320"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="09212-102">COR_GC_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="09212-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="09212-103">Enthält Informationen zu einem Objekt, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="09212-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09212-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09212-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="09212-105">Members</span><span class="sxs-lookup"><span data-stu-id="09212-105">Members</span></span>  
  
|<span data-ttu-id="09212-106">Member</span><span class="sxs-lookup"><span data-stu-id="09212-106">Member</span></span>|<span data-ttu-id="09212-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09212-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="09212-108">Ein Zeiger auf die Anwendungsdomäne, zu der das Handle oder Objekt gehört.</span><span class="sxs-lookup"><span data-stu-id="09212-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="09212-109">Sein Wert `null`kann .</span><span class="sxs-lookup"><span data-stu-id="09212-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="09212-110">Entweder eine ICorDebugValue- oder eine ICorDebugReferenceValue-Schnittstelle, die dem zu garbagecollected Objekt entspricht.</span><span class="sxs-lookup"><span data-stu-id="09212-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="09212-111">Ein [CorGCReferenceType](corgcreferencetype-enumeration.md) CorGCReferenceType-Enumerationswert, der angibt, woher der Stamm stammt.</span><span class="sxs-lookup"><span data-stu-id="09212-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="09212-112">Weitere Informationen finden Sie im Abschnitt mit Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="09212-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="09212-113">Zusätzliche Daten über das Objekt, das Garbage Collection sein soll.</span><span class="sxs-lookup"><span data-stu-id="09212-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="09212-114">Diese Informationen hängen von der Quelle des `type` Objekts ab, wie im Feld angegeben.</span><span class="sxs-lookup"><span data-stu-id="09212-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="09212-115">Weitere Informationen finden Sie im Abschnitt mit Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="09212-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09212-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="09212-116">Remarks</span></span>  
 <span data-ttu-id="09212-117">Das `type` Feld ist ein CorGCReferenceType-Enumerationswert, der angibt, woher der Verweis stammt. [CorGCReferenceType](corgcreferencetype-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="09212-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="09212-118">Ein `COR_GC_REFERENCE` bestimmter Wert kann eine der folgenden Arten von verwalteten Objekten widerspiegeln:</span><span class="sxs-lookup"><span data-stu-id="09212-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="09212-119">Objekte aus allen verwalteten Stacks (`CorGCReferenceType.CorReferenceStack`).</span><span class="sxs-lookup"><span data-stu-id="09212-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="09212-120">Dazu gehören Live-Referenzen in verwaltetem Code sowie Objekte, die von der Common Language Runtime erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="09212-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="09212-121">Objekte aus der`CorGCReferenceType.CorHandle*`Handle-Tabelle ( ).</span><span class="sxs-lookup"><span data-stu-id="09212-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="09212-122">Dazu gehören starke`HNDTYPE_STRONG` `HNDTYPE_REFCOUNT`Referenzen ( und ) und statische Variablen in einem Modul.</span><span class="sxs-lookup"><span data-stu-id="09212-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="09212-123">Objekte aus der Finalizerwarteschlange (`CorGCReferenceType.CorReferenceFinalizer`).</span><span class="sxs-lookup"><span data-stu-id="09212-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="09212-124">Die Finalizer-Warteschlangen-Roots-Objekte, bis der Finalizer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="09212-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="09212-125">Das `extraData` Feld enthält zusätzliche Daten, abhängig von der Quelle (oder dem Typ) des Verweises.</span><span class="sxs-lookup"><span data-stu-id="09212-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="09212-126">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="09212-126">Possible values are:</span></span>  
  
- <span data-ttu-id="09212-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="09212-127">`DependentSource`.</span></span> <span data-ttu-id="09212-128">Wenn `type` die `CorGCREferenceType.CorHandleStrongDependent`ist , ist dieses Feld das Objekt, das, wenn `COR_GC_REFERENCE.Location`es noch lebt, das Objekt entwurzelt, das garbage-collection bei sein soll.</span><span class="sxs-lookup"><span data-stu-id="09212-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="09212-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="09212-129">`RefCount`.</span></span> <span data-ttu-id="09212-130">Wenn `type` der `CorGCREferenceType.CorHandleStrongRefCount`ist , ist dieses Feld die Referenzanzahl des Handles.</span><span class="sxs-lookup"><span data-stu-id="09212-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="09212-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="09212-131">`Size`.</span></span> <span data-ttu-id="09212-132">Wenn `type` der `CorGCREferenceType.CorHandleStrongSizedByref`ist , ist dieses Feld die letzte Größe der Objektstruktur, für die der Garbage Collector die Objektwurzeln berechnet hat.</span><span class="sxs-lookup"><span data-stu-id="09212-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="09212-133">Beachten Sie, dass diese Berechnung nicht unbedingt auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="09212-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09212-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="09212-134">Requirements</span></span>  
 <span data-ttu-id="09212-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09212-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09212-136">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09212-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09212-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09212-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09212-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09212-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09212-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09212-139">See also</span></span>

- [<span data-ttu-id="09212-140">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="09212-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="09212-141">Debuggen</span><span class="sxs-lookup"><span data-stu-id="09212-141">Debugging</span></span>](index.md)
