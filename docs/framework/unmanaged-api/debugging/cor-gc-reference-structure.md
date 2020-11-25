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
ms.openlocfilehash: bb4a8f7ff3ee54474804e3e5620dcce7c9f79fb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726612"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="74a55-102">COR_GC_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="74a55-102">COR_GC_REFERENCE Structure</span></span>

<span data-ttu-id="74a55-103">Enthält Informationen zu einem Objekt, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="74a55-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74a55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74a55-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="74a55-105">Member</span><span class="sxs-lookup"><span data-stu-id="74a55-105">Members</span></span>  
  
|<span data-ttu-id="74a55-106">Member</span><span class="sxs-lookup"><span data-stu-id="74a55-106">Member</span></span>|<span data-ttu-id="74a55-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="74a55-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="74a55-108">Ein Zeiger auf die Anwendungsdomäne, zu der das Handle oder das Objekt gehört.</span><span class="sxs-lookup"><span data-stu-id="74a55-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="74a55-109">Der Wert kann sein `null` .</span><span class="sxs-lookup"><span data-stu-id="74a55-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="74a55-110">Eine ICorDebugValue-oder ICorDebugReferenceValue-Schnittstelle, die dem Objekt entspricht, das in die Garbage Collection aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="74a55-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="74a55-111">Ein [corgkreferencetype](corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, woher der Stamm stammt.</span><span class="sxs-lookup"><span data-stu-id="74a55-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="74a55-112">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="74a55-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="74a55-113">Zusätzliche Daten zu dem Objekt, für das die Garbage Collection durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="74a55-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="74a55-114">Diese Informationen hängen von der Quelle des Objekts ab, wie im Feld angegeben `type` .</span><span class="sxs-lookup"><span data-stu-id="74a55-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="74a55-115">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="74a55-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74a55-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74a55-116">Remarks</span></span>  

 <span data-ttu-id="74a55-117">Das `type` Feld ist ein [corgkreferencetype](corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, woher der Verweis stammt.</span><span class="sxs-lookup"><span data-stu-id="74a55-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="74a55-118">Ein bestimmter `COR_GC_REFERENCE` Wert kann eine der folgenden Arten von verwalteten Objekten widerspiegeln:</span><span class="sxs-lookup"><span data-stu-id="74a55-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="74a55-119">Objekte aus allen verwalteten Stapeln ( `CorGCReferenceType.CorReferenceStack` ).</span><span class="sxs-lookup"><span data-stu-id="74a55-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="74a55-120">Dies schließt sowohl Live Verweise in verwaltetem Code als auch Objekte ein, die vom Common Language Runtime erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="74a55-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="74a55-121">Objekte aus der Handle-Tabelle ( `CorGCReferenceType.CorHandle*` ).</span><span class="sxs-lookup"><span data-stu-id="74a55-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="74a55-122">Dies schließt starke Verweise ( `HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT` ) sowie statische Variablen in einem Modul ein.</span><span class="sxs-lookup"><span data-stu-id="74a55-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="74a55-123">Objekte aus der Finalizerwarteschlange ( `CorGCReferenceType.CorReferenceFinalizer` ).</span><span class="sxs-lookup"><span data-stu-id="74a55-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="74a55-124">Die Finalizer-Warteschlange wurzelt Objekte, bis der Finalizer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="74a55-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="74a55-125">Das `extraData` Feld enthält zusätzliche Daten, abhängig von der Quelle (oder dem Typ) des Verweises.</span><span class="sxs-lookup"><span data-stu-id="74a55-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="74a55-126">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="74a55-126">Possible values are:</span></span>  
  
- <span data-ttu-id="74a55-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="74a55-127">`DependentSource`.</span></span> <span data-ttu-id="74a55-128">Wenn den `type` Wert `CorGCREferenceType.CorHandleStrongDependent` hat, ist dieses Feld das Objekt, das, wenn es aktiv ist, das Objekt, für das die Garbage Collection durchgeführt werden soll `COR_GC_REFERENCE.Location` .</span><span class="sxs-lookup"><span data-stu-id="74a55-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="74a55-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="74a55-129">`RefCount`.</span></span> <span data-ttu-id="74a55-130">Wenn den `type` Wert `CorGCREferenceType.CorHandleStrongRefCount` hat, ist dieses Feld der Verweis Zähler des Handles.</span><span class="sxs-lookup"><span data-stu-id="74a55-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="74a55-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="74a55-131">`Size`.</span></span> <span data-ttu-id="74a55-132">Wenn den `type` Wert `CorGCREferenceType.CorHandleStrongSizedByref` hat, ist dieses Feld die letzte Größe der Objektstruktur, für die der Garbage Collector die Objekt Stämme berechnet hat.</span><span class="sxs-lookup"><span data-stu-id="74a55-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="74a55-133">Beachten Sie, dass diese Berechnung nicht unbedingt auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="74a55-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74a55-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="74a55-134">Requirements</span></span>  

 <span data-ttu-id="74a55-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74a55-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74a55-136">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74a55-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74a55-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74a55-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74a55-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74a55-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74a55-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74a55-139">See also</span></span>

- [<span data-ttu-id="74a55-140">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="74a55-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="74a55-141">Debuggen</span><span class="sxs-lookup"><span data-stu-id="74a55-141">Debugging</span></span>](index.md)
