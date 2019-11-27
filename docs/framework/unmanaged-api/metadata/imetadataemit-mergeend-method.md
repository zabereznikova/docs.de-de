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
ms.openlocfilehash: 34ecfc2f01f22971e135358806adeea632e02f8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448038"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="6b351-102">IMetaDataEmit::MergeEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="6b351-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="6b351-103">Führt alle Metadatenbereiche, die von einem oder mehreren vorherigen Aufrufen von [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)angegeben werden, in den aktuellen Bereich zusammen.</span><span class="sxs-lookup"><span data-stu-id="6b351-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="6b351-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b351-104">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="6b351-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b351-105">Parameters</span></span>

<span data-ttu-id="6b351-106">Diese Methode nimmt keine Parameter an.</span><span class="sxs-lookup"><span data-stu-id="6b351-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b351-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b351-107">Remarks</span></span>

<span data-ttu-id="6b351-108">Diese Routine löst die tatsächliche Zusammenführung von Metadaten für alle Import Bereiche aus, die durch vorherige Aufrufe von `IMetaDataEmit::Merge`angegeben sind, in den aktuellen Ausgabebereich.</span><span class="sxs-lookup"><span data-stu-id="6b351-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="6b351-109">Die folgenden speziellen Bedingungen gelten für den Merge:</span><span class="sxs-lookup"><span data-stu-id="6b351-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="6b351-110">Ein Modul Versions Bezeichner (MVID) wird nie importiert, da er für die Metadaten im Import Bereich eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="6b351-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="6b351-111">Keine vorhandenen Modul weiten Eigenschaften werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b351-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="6b351-112">Wenn Modul Eigenschaften bereits für den aktuellen Gültigkeitsbereich festgelegt wurden, werden keine Modul Eigenschaften importiert.</span><span class="sxs-lookup"><span data-stu-id="6b351-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="6b351-113">Wenn jedoch Modul Eigenschaften im aktuellen Bereich nicht festgelegt wurden, werden Sie nur einmal importiert, wenn Sie zum ersten Mal gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="6b351-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="6b351-114">Wenn diese Modul Eigenschaften wieder gefunden werden, sind Sie Duplikate.</span><span class="sxs-lookup"><span data-stu-id="6b351-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="6b351-115">Wenn die Werte aller Modul Eigenschaften (außer MVID) verglichen werden und keine Duplikate gefunden werden, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6b351-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="6b351-116">Für Typdefinitionen (`TypeDef`) werden keine Duplikate im aktuellen Bereich zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="6b351-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="6b351-117">`TypeDef` Objekte werden für jeden *voll qualifizierten Objektnamen* + *GUID* + *Versionsnummer*auf Duplikate überprüft.</span><span class="sxs-lookup"><span data-stu-id="6b351-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="6b351-118">Wenn eine Entsprechung für "Name" oder "GUID" vorliegt und eines der beiden anderen Elemente unterschiedlich ist, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6b351-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="6b351-119">Wenn alle drei Elemente übereinstimmen, führt `MergeEnd` eine kurze Prüfung durch, um sicherzustellen, dass es sich bei den Einträgen tatsächlich um Duplikate handelt. Andernfalls wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6b351-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="6b351-120">Diese flüchtige Prüfung sucht nach:</span><span class="sxs-lookup"><span data-stu-id="6b351-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="6b351-121">Dieselben Member-Deklarationen, die in derselben Reihenfolge auftreten.</span><span class="sxs-lookup"><span data-stu-id="6b351-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="6b351-122">Member, die als `mdPrivateScope` gekennzeichnet sind (siehe die [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) -Enumeration), sind in dieser Überprüfung nicht enthalten. Sie werden speziell zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="6b351-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="6b351-123">Das gleiche Klassen Layout.</span><span class="sxs-lookup"><span data-stu-id="6b351-123">The same class layout.</span></span>

  <span data-ttu-id="6b351-124">Dies bedeutet, dass ein `TypeDef` Objekt immer vollständig und konsistent in jedem Metadatenbereich definiert werden muss, in dem es deklariert ist. Wenn seine Member-Implementierungen (für eine Klasse) auf mehrere Kompilierungs Einheiten verteilt sind, wird davon ausgegangen, dass die vollständige Definition in jedem Bereich vorhanden und nicht in jedem Bereich inkrementell ist.</span><span class="sxs-lookup"><span data-stu-id="6b351-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="6b351-125">Wenn z. b. Parameternamen für den Vertrag relevant sind, müssen Sie in jedem Bereich auf dieselbe Weise ausgegeben werden. Wenn Sie nicht relevant sind, sollten Sie nicht in Metadaten ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6b351-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="6b351-126">Eine Ausnahme besteht darin, dass für ein `TypeDef` Objekt inkrementelle Member als `mdPrivateScope`gekennzeichnet werden können.</span><span class="sxs-lookup"><span data-stu-id="6b351-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="6b351-127">Beim begegnen werden `MergeEnd` inkrementell dem aktuellen Gültigkeitsbereich hinzugefügt, ohne dass Duplikate berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="6b351-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="6b351-128">Da der Compiler den privaten Bereich versteht, muss der Compiler für die Erzwingung von Regeln verantwortlich sein.</span><span class="sxs-lookup"><span data-stu-id="6b351-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="6b351-129">Relative virtuelle Adressen (RVAs) werden nicht importiert oder zusammengeführt. der Compiler erwartet, dass diese Informationen erneut ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6b351-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="6b351-130">Benutzerdefinierte Attribute werden nur zusammengeführt, wenn das Element, an das Sie angefügt sind, zusammengeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6b351-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="6b351-131">Beispielsweise werden benutzerdefinierte Attribute, die einer-Klasse zugeordnet sind, beim ersten Auftreten der-Klasse zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="6b351-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="6b351-132">Wenn benutzerdefinierte Attribute einer `TypeDef` oder `MemberDef` zugeordnet sind, die spezifisch für die Kompilierungseinheit ist (z. b. der Zeitstempel eines kompilierten Members), werden Sie nicht zusammengeführt, und der Compiler muss solche Metadaten entfernen oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6b351-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="6b351-133">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6b351-133">Requirements</span></span>

<span data-ttu-id="6b351-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b351-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6b351-135">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6b351-135">**Header:** Cor.h</span></span>

<span data-ttu-id="6b351-136">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b351-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="6b351-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b351-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6b351-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b351-138">See also</span></span>

- [<span data-ttu-id="6b351-139">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b351-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6b351-140">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b351-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
