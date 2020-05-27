---
title: IMetaDataEmit::MergeEnd-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
ms.openlocfilehash: feb81b86190f953b50f43f244f4e58a0a482f86e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003918"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="d5db5-102">IMetaDataEmit::MergeEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="d5db5-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="d5db5-103">Führt alle Metadatenbereiche, die von einem oder mehreren vorherigen Aufrufen von [IMetaDataEmit:: Merge](imetadataemit-merge-method.md)angegeben werden, in den aktuellen Bereich zusammen.</span><span class="sxs-lookup"><span data-stu-id="d5db5-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="d5db5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5db5-104">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="d5db5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5db5-105">Parameters</span></span>

<span data-ttu-id="d5db5-106">Diese Methode nimmt keine Parameter an.</span><span class="sxs-lookup"><span data-stu-id="d5db5-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5db5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5db5-107">Remarks</span></span>

<span data-ttu-id="d5db5-108">Diese Routine löst die tatsächliche Zusammenführung von Metadaten für alle Import Bereiche aus, die durch vorherige Aufrufe von angegeben `IMetaDataEmit::Merge` werden, in den aktuellen Ausgabebereich.</span><span class="sxs-lookup"><span data-stu-id="d5db5-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="d5db5-109">Die folgenden speziellen Bedingungen gelten für den Merge:</span><span class="sxs-lookup"><span data-stu-id="d5db5-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="d5db5-110">Ein Modul Versions Bezeichner (MVID) wird nie importiert, da er für die Metadaten im Import Bereich eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="d5db5-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="d5db5-111">Keine vorhandenen Modul weiten Eigenschaften werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5db5-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="d5db5-112">Wenn Modul Eigenschaften bereits für den aktuellen Gültigkeitsbereich festgelegt wurden, werden keine Modul Eigenschaften importiert.</span><span class="sxs-lookup"><span data-stu-id="d5db5-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="d5db5-113">Wenn jedoch Modul Eigenschaften im aktuellen Bereich nicht festgelegt wurden, werden Sie nur einmal importiert, wenn Sie zum ersten Mal gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="d5db5-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="d5db5-114">Wenn diese Modul Eigenschaften wieder gefunden werden, sind Sie Duplikate.</span><span class="sxs-lookup"><span data-stu-id="d5db5-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="d5db5-115">Wenn die Werte aller Modul Eigenschaften (außer MVID) verglichen werden und keine Duplikate gefunden werden, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d5db5-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="d5db5-116">Für Typdefinitionen ( `TypeDef` ) werden keine Duplikate im aktuellen Bereich zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="d5db5-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="d5db5-117">`TypeDef`Objekte werden für jede *voll qualifizierte Objektnamen*-  +  *GUID*-  +  *Versionsnummer*auf Duplikate überprüft.</span><span class="sxs-lookup"><span data-stu-id="d5db5-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="d5db5-118">Wenn eine Entsprechung für "Name" oder "GUID" vorliegt und eines der beiden anderen Elemente unterschiedlich ist, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d5db5-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="d5db5-119">Wenn alle drei Elemente übereinstimmen, `MergeEnd` wird von eine kurze Prüfung durchführt, um sicherzustellen, dass es sich bei den Einträgen tatsächlich um Duplikate handelt. andernfalls wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d5db5-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="d5db5-120">Diese flüchtige Prüfung sucht nach:</span><span class="sxs-lookup"><span data-stu-id="d5db5-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="d5db5-121">Dieselben Member-Deklarationen, die in derselben Reihenfolge auftreten.</span><span class="sxs-lookup"><span data-stu-id="d5db5-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="d5db5-122">Member, die als gekennzeichnet sind `mdPrivateScope` (siehe die [CorMethodAttr](cormethodattr-enumeration.md) -Enumeration), werden in dieser Überprüfung nicht berücksichtigt. Sie werden speziell zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="d5db5-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="d5db5-123">Das gleiche Klassen Layout.</span><span class="sxs-lookup"><span data-stu-id="d5db5-123">The same class layout.</span></span>

  <span data-ttu-id="d5db5-124">Dies bedeutet, dass ein `TypeDef` -Objekt immer vollständig und konsistent in jedem Metadatenbereich definiert werden muss, in dem es deklariert ist. wenn seine Member-Implementierungen (für eine Klasse) auf mehrere Kompilierungs Einheiten verteilt sind, wird davon ausgegangen, dass die vollständige Definition in jedem Bereich vorhanden und nicht in jedem Bereich inkrementell ist.</span><span class="sxs-lookup"><span data-stu-id="d5db5-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="d5db5-125">Wenn z. b. Parameternamen für den Vertrag relevant sind, müssen Sie in jedem Bereich auf dieselbe Weise ausgegeben werden. Wenn Sie nicht relevant sind, sollten Sie nicht in Metadaten ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d5db5-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="d5db5-126">Die Ausnahme besteht darin, dass für ein- `TypeDef` Objekt inkrementelle Member als gekennzeichnet werden können `mdPrivateScope` .</span><span class="sxs-lookup"><span data-stu-id="d5db5-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="d5db5-127">Beim begegnen werden diese `MergeEnd` inkrementell dem aktuellen Bereich hinzugefügt, ohne dass Duplikate berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="d5db5-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="d5db5-128">Da der Compiler den privaten Bereich versteht, muss der Compiler für die Erzwingung von Regeln verantwortlich sein.</span><span class="sxs-lookup"><span data-stu-id="d5db5-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="d5db5-129">Relative virtuelle Adressen (RVAs) werden nicht importiert oder zusammengeführt. der Compiler erwartet, dass diese Informationen erneut ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d5db5-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="d5db5-130">Benutzerdefinierte Attribute werden nur zusammengeführt, wenn das Element, an das Sie angefügt sind, zusammengeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d5db5-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="d5db5-131">Beispielsweise werden benutzerdefinierte Attribute, die einer-Klasse zugeordnet sind, beim ersten Auftreten der-Klasse zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="d5db5-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="d5db5-132">Wenn benutzerdefinierte Attribute einem oder zugeordnet `TypeDef` sind `MemberDef` , das für die Kompilierungseinheit spezifisch ist (z. b. der Zeitstempel eines kompilierten Members), werden Sie nicht zusammengeführt, und der Compiler muss solche Metadaten entfernen oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d5db5-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="d5db5-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d5db5-133">Requirements</span></span>

<span data-ttu-id="d5db5-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5db5-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d5db5-135">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d5db5-135">**Header:** Cor.h</span></span>

<span data-ttu-id="d5db5-136">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5db5-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="d5db5-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5db5-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d5db5-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5db5-138">See also</span></span>

- [<span data-ttu-id="d5db5-139">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5db5-139">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d5db5-140">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5db5-140">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
