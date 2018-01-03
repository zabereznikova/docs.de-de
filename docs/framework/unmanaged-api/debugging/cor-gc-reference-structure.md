---
title: COR_GC_REFERENCE-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_REFERENCE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_GC_REFERENCE
helpviewer_keywords: COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a86604febb7641eef147608e564a27883fdc4bec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreference-structure"></a><span data-ttu-id="bbe45-102">COR_GC_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="bbe45-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="bbe45-103">Enthält Informationen zu einem Objekt, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bbe45-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbe45-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bbe45-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="bbe45-105">Member</span><span class="sxs-lookup"><span data-stu-id="bbe45-105">Members</span></span>  
  
|<span data-ttu-id="bbe45-106">Member</span><span class="sxs-lookup"><span data-stu-id="bbe45-106">Member</span></span>|<span data-ttu-id="bbe45-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbe45-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="bbe45-108">Ein Zeiger auf die Anwendungsdomäne, zu der das Handle oder das Objekt gehört.</span><span class="sxs-lookup"><span data-stu-id="bbe45-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="bbe45-109">Der Wert möglicherweise `null`.</span><span class="sxs-lookup"><span data-stu-id="bbe45-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="bbe45-110">ICorDebugValue oder ein [ICorDebugReferenceValue-Schnittstelle, die das Objekt, das speicherbereinigt werden soll entspricht.</span><span class="sxs-lookup"><span data-stu-id="bbe45-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="bbe45-111">Ein [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, in dem Stammverzeichnis stammt.</span><span class="sxs-lookup"><span data-stu-id="bbe45-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="bbe45-112">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="bbe45-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="bbe45-113">Zusätzliche Daten über das Objekt, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bbe45-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="bbe45-114">Diese Informationen hängt von der Quelle des Objekts, die durch die `type` Feld.</span><span class="sxs-lookup"><span data-stu-id="bbe45-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="bbe45-115">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="bbe45-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbe45-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bbe45-116">Remarks</span></span>  
 <span data-ttu-id="bbe45-117">Die `type` Feld ist eine [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Enumerationswert, der angibt, in dem der Verweis stammt.</span><span class="sxs-lookup"><span data-stu-id="bbe45-117">The `type` field is a [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="bbe45-118">Ein bestimmter `COR_GC_REFERENCE` Wert reflektiert die folgenden Arten von verwalteten Objekten:</span><span class="sxs-lookup"><span data-stu-id="bbe45-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
-   <span data-ttu-id="bbe45-119">Objekte aus allen verwalteten Stapeln (`CorGCReferenceType.CorReferenceStack`).</span><span class="sxs-lookup"><span data-stu-id="bbe45-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="bbe45-120">Dies schließt die aktive Verweise in verwaltetem Code als auch Objekte, die von der common Language Runtime erstellt.</span><span class="sxs-lookup"><span data-stu-id="bbe45-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="bbe45-121">Objekte aus der Handletabelle (`CorGCReferenceType.CorHandle*`).</span><span class="sxs-lookup"><span data-stu-id="bbe45-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="bbe45-122">Dies schließt starken Verweise (`HNDTYPE_STRONG` und `HNDTYPE_REFCOUNT`) und statische Variablen in einem Modul.</span><span class="sxs-lookup"><span data-stu-id="bbe45-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="bbe45-123">Objekte aus der Finalizerwarteschlange (`CorGCReferenceType.CorReferenceFinalizer`).</span><span class="sxs-lookup"><span data-stu-id="bbe45-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="bbe45-124">Die Finalizer-Warteschlange Stämme Objekte auf, bis der Finalizer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbe45-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="bbe45-125">Die `extraData` Feld enthält zusätzliche Daten abhängig von der Quelle (oder Typ) des Verweises.</span><span class="sxs-lookup"><span data-stu-id="bbe45-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="bbe45-126">Dabei sind folgende Werte möglich:</span><span class="sxs-lookup"><span data-stu-id="bbe45-126">Possible values are:</span></span>  
  
-   <span data-ttu-id="bbe45-127">`DependentSource`</span><span class="sxs-lookup"><span data-stu-id="bbe45-127">`DependentSource`.</span></span> <span data-ttu-id="bbe45-128">Wenn die `type` ist `CorGCREferenceType.CorHandleStrongDependent`, dieses Feld ist das Objekt, das, wenn aktiv, wird das Objekt, um zur Garbage Collection werden Stämme `COR_GC_REFERENCE.Location`.</span><span class="sxs-lookup"><span data-stu-id="bbe45-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
-   <span data-ttu-id="bbe45-129">`RefCount`</span><span class="sxs-lookup"><span data-stu-id="bbe45-129">`RefCount`.</span></span> <span data-ttu-id="bbe45-130">Wenn die `type` ist `CorGCREferenceType.CorHandleStrongRefCount`, dieses Feld wird der Verweiszähler des Handles.</span><span class="sxs-lookup"><span data-stu-id="bbe45-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
-   <span data-ttu-id="bbe45-131">`Size`</span><span class="sxs-lookup"><span data-stu-id="bbe45-131">`Size`.</span></span> <span data-ttu-id="bbe45-132">Wenn die `type` ist `CorGCREferenceType.CorHandleStrongSizedByref`, dieses Feld ist die letzte Größe der Objektstruktur für den Garbage Collector die Stämme Objekt berechnet.</span><span class="sxs-lookup"><span data-stu-id="bbe45-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="bbe45-133">Beachten Sie, dass diese Berechnung nicht unbedingt auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="bbe45-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbe45-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bbe45-134">Requirements</span></span>  
 <span data-ttu-id="bbe45-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbe45-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbe45-136">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbe45-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbe45-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbe45-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbe45-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbe45-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe45-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbe45-139">See Also</span></span>  
 [<span data-ttu-id="bbe45-140">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="bbe45-140">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="bbe45-141">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bbe45-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
