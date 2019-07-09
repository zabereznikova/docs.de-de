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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99c1decf27685f027d6baa8412bf20fdf693d161
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664021"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="5b2e6-102">IMetaDataEmit::MergeEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="5b2e6-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="5b2e6-103">Merges im aktuellen Bereich alle Metadatenbereiche, die durch eine oder mehrere früheren aufrufen angegeben [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="5b2e6-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="5b2e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b2e6-104">Syntax</span></span>

```cpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="5b2e6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b2e6-105">Parameters</span></span>

<span data-ttu-id="5b2e6-106">Diese Methode akzeptiert keine Parameter.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b2e6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b2e6-107">Remarks</span></span>

<span data-ttu-id="5b2e6-108">Diese Routine wird ausgelöst, das tatsächliche Zusammenführen der Metadaten, importieren Sie alle Aufrufe von abgrenzen, indem Sie angegebenen Bereiche `IMetaDataEmit::Merge`, in den aktuellen Ausgabebereich.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="5b2e6-109">Die folgenden speziellen Bedingungen gelten für die Zusammenführung:</span><span class="sxs-lookup"><span data-stu-id="5b2e6-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="5b2e6-110">Ein Modul Versions-ID (MVID) ist noch nie importiert, da er auf die Metadaten im Importbereich eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="5b2e6-111">Keine vorhandenen Modul-Wide-Eigenschaften werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="5b2e6-112">Wenn die Moduleigenschaften für den aktuellen Bereich bereits festgelegt wurden, werden keine Eigenschaften des Moduls importiert.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="5b2e6-113">Wenn die Moduleigenschaften im aktuellen Bereich nicht festgelegt wurden, werden sie jedoch importiert nur einmal auf, wenn sie zuerst erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="5b2e6-114">Die Moduleigenschaften erneut auftreten, werden Duplikate.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="5b2e6-115">Wenn die Werte aller Eigenschaften des Moduls (mit Ausnahme der MVID) verglichen werden und keine Duplikate gefunden werden, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="5b2e6-116">Für Typdefinitionen (`TypeDef`), keine Duplikate in den aktuellen Bereich zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="5b2e6-117">`TypeDef` Objekte mit jeweils auf Duplikate überprüft werden *vollständig qualifizierter Objektname* + *GUID* + *Versionsnummer*.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="5b2e6-118">Wenn eine Übereinstimmung auf Namen oder GUID vorhanden ist und keines der anderen beiden Elemente unterscheidet, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="5b2e6-119">Wenn alle drei Elemente übereinstimmen, andernfalls `MergeEnd` ist eine oberflächliche, um sicherzustellen, dass die Einträge sind in der Tat Duplikate; Falls nicht, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="5b2e6-120">Diese kurze Überprüfung sucht nach:</span><span class="sxs-lookup"><span data-stu-id="5b2e6-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="5b2e6-121">Die gleichen Memberdeklarationen, die in der gleichen Reihenfolge auftreten.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="5b2e6-122">Elemente, die als gekennzeichnet sind `mdPrivateScope` (finden Sie unter den [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) Enumeration) befinden sich nicht bei dieser Überprüfung; sie speziell zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="5b2e6-123">Das Klassenlayout für dieselbe.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-123">The same class layout.</span></span>

  <span data-ttu-id="5b2e6-124">Dies bedeutet, dass eine `TypeDef` Objekt muss immer vollständig und konsistent definiert werden in jedem Metadatenbereich in dem sie deklariert wird, wenn die Implementierungen von Membern (für eine Klasse) über mehrere Kompilierungseinheiten hinweg verteilt sind, die vollständige Definition wird als in jedem Bereich vorhanden und können mit jeder Bereich nicht inkrementell.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="5b2e6-125">Z. B. wenn Parameternamen für den Vertrag relevant sind, müssen sie die gleiche Weise wie in jedem Bereich ausgegeben werden; Wenn sie nicht relevant sind, sollten sie nicht in Metadaten ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="5b2e6-126">Die Ausnahme ist, dass eine `TypeDef` Objekt kann inkrementelle als Mitglieder haben `mdPrivateScope`.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="5b2e6-127">Bei diesen `MergeEnd` inkrementell auf den aktuellen Bereich ohne Berücksichtigung von Duplikaten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="5b2e6-128">Da der Compiler den privaten Bereich versteht, muss der Compiler zum Erzwingen von Regeln verantwortlich sein.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="5b2e6-129">Relative virtuelle Adresse (RVA) werden nicht importiert oder zusammengeführt; der Compiler muss diese Informationen erneut ausgeben.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="5b2e6-130">Benutzerdefinierte Attribute werden zusammengeführt, nur, wenn das Element, mit dem sie verbunden sind, zusammengeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="5b2e6-131">Beispielsweise werden benutzerdefinierte Attribute einer Klasse zusammengeführt, wenn die Klasse zuerst erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="5b2e6-132">Wenn Sie benutzerdefinierte Attribute zugewiesen sind eine `TypeDef` oder `MemberDef` , der die Kompilierungseinheit (z. B. der Zeitstempel, der eine Memberkompilierung) spezifisch ist, werden sie nicht zusammengeführt, und es obliegt des Compilers solche Metadaten entfernen oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5b2e6-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="5b2e6-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b2e6-133">Requirements</span></span>

<span data-ttu-id="5b2e6-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b2e6-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="5b2e6-135">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5b2e6-135">**Header:** Cor.h</span></span>

<span data-ttu-id="5b2e6-136">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5b2e6-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="5b2e6-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b2e6-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5b2e6-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b2e6-138">See also</span></span>

- [<span data-ttu-id="5b2e6-139">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b2e6-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5b2e6-140">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b2e6-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
