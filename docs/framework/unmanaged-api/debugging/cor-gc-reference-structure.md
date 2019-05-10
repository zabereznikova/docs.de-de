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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 848765a4ea9657020bd84e476f992ae69750dda9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617696"
---
# <a name="corgcreference-structure"></a><span data-ttu-id="cbe1c-102">COR_GC_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="cbe1c-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="cbe1c-103">Enthält Informationen zu einem Objekt, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbe1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbe1c-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="cbe1c-105">Member</span><span class="sxs-lookup"><span data-stu-id="cbe1c-105">Members</span></span>  
  
|<span data-ttu-id="cbe1c-106">Member</span><span class="sxs-lookup"><span data-stu-id="cbe1c-106">Member</span></span>|<span data-ttu-id="cbe1c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbe1c-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="cbe1c-108">Ein Zeiger auf die Anwendungsdomäne, zu der das Handle oder das Objekt gehört.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="cbe1c-109">Der Wert möglicherweise `null`.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="cbe1c-110">ICorDebugValue- oder eine ICorDebugReferenceValue-Schnittstelle, die das Objekt, das speicherbereinigt werden soll entspricht.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="cbe1c-111">Ein [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, woher das Stammverzeichnis stammen.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="cbe1c-112">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="cbe1c-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="cbe1c-113">Zusätzliche Daten über das Objekt, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="cbe1c-114">Diese Informationen hängen von der Quelle des Objekts, die durch die `type` Feld.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="cbe1c-115">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="cbe1c-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbe1c-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cbe1c-116">Remarks</span></span>  
 <span data-ttu-id="cbe1c-117">Die `type` Feld ist ein [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, in dem der Verweis stammt.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-117">The `type` field is a [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="cbe1c-118">Eine bestimmte `COR_GC_REFERENCE` Wert kann eine der folgenden Arten von verwalteten Objekten widerspiegeln:</span><span class="sxs-lookup"><span data-stu-id="cbe1c-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="cbe1c-119">Objekte aus allen verwalteten Stapel (`CorGCReferenceType.CorReferenceStack`).</span><span class="sxs-lookup"><span data-stu-id="cbe1c-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="cbe1c-120">Dies schließt die aktiven Verweise in verwaltetem Code als auch Objekte, die von der common Language Runtime erstellt.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="cbe1c-121">Objekte aus der Handletabelle (`CorGCReferenceType.CorHandle*`).</span><span class="sxs-lookup"><span data-stu-id="cbe1c-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="cbe1c-122">Dies schließt starken Verweise (`HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT`) und statische Variablen in einem Modul.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="cbe1c-123">Objekte aus der Finalizerwarteschlange (`CorGCReferenceType.CorReferenceFinalizer`).</span><span class="sxs-lookup"><span data-stu-id="cbe1c-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="cbe1c-124">Die Finalizer-Warteschlange Stämme Objekte an, bis der Finalizer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="cbe1c-125">Die `extraData` Feld enthält die zusätzliche Daten abhängig von der Quelle (oder Typ) des Verweises.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="cbe1c-126">Dabei sind folgende Werte möglich:</span><span class="sxs-lookup"><span data-stu-id="cbe1c-126">Possible values are:</span></span>  
  
- <span data-ttu-id="cbe1c-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-127">`DependentSource`.</span></span> <span data-ttu-id="cbe1c-128">Wenn die `type` ist `CorGCREferenceType.CorHandleStrongDependent`, dieses Feld ist das Objekt, das, wenn aktiv ist, wird das Objekt, um die Garbage Collection auf Stammelemente `COR_GC_REFERENCE.Location`.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="cbe1c-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-129">`RefCount`.</span></span> <span data-ttu-id="cbe1c-130">Wenn die `type` ist `CorGCREferenceType.CorHandleStrongRefCount`, dieses Feld wird der Verweiszähler des Handles.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="cbe1c-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-131">`Size`.</span></span> <span data-ttu-id="cbe1c-132">Wenn die `type` ist `CorGCREferenceType.CorHandleStrongSizedByref`, dieses Feld ist die letzte Größe der Objektstruktur, die für den Garbage Collector die Stämme Objekt berechnet.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="cbe1c-133">Beachten Sie, dass diese Berechnung nicht unbedingt auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="cbe1c-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbe1c-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cbe1c-134">Requirements</span></span>  
 <span data-ttu-id="cbe1c-135">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbe1c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbe1c-136">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbe1c-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbe1c-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbe1c-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbe1c-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbe1c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe1c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbe1c-139">See also</span></span>

- [<span data-ttu-id="cbe1c-140">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="cbe1c-140">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="cbe1c-141">Debuggen</span><span class="sxs-lookup"><span data-stu-id="cbe1c-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
