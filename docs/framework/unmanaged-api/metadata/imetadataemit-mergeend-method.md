---
title: IMetaDataEmit::MergeEnd-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.MergeEnd
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 265fc007b5817e8dffd5846738a7a0003bbddf9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="705b5-102">IMetaDataEmit::MergeEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="705b5-102">IMetaDataEmit::MergeEnd Method</span></span>
<span data-ttu-id="705b5-103">Führt den aktuellen Bereich alle Metadatenbereiche, die durch eine oder mehrere vorherigen Aufrufe von angegeben [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="705b5-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="705b5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="705b5-104">Syntax</span></span>  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a><span data-ttu-id="705b5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="705b5-105">Parameters</span></span>  
 <span data-ttu-id="705b5-106">Diese Methode nimmt keine Parameter.</span><span class="sxs-lookup"><span data-stu-id="705b5-106">This method takes no parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="705b5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="705b5-107">Remarks</span></span>  
 <span data-ttu-id="705b5-108">Diese Routine löst das eigentliche Zusammenführen von Metadaten, importieren Sie alle angegebenen Aufrufe abgrenzen, indem Sie Bereiche `IMetaDataEmit::Merge`, in der aktuellen Ausgabebereich.</span><span class="sxs-lookup"><span data-stu-id="705b5-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>  
  
 <span data-ttu-id="705b5-109">Die folgenden speziellen Bedingungen gelten für die Zusammenführung:</span><span class="sxs-lookup"><span data-stu-id="705b5-109">The following special conditions apply to the merge:</span></span>  
  
-   <span data-ttu-id="705b5-110">Ein Modul Versions-ID (MVID) wird noch nie importiert, da er auf die Metadaten im Importbereich eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="705b5-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>  
  
-   <span data-ttu-id="705b5-111">Keine vorhandenen Modul gesamten-Eigenschaften werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="705b5-111">No existing module-wide properties are overwritten.</span></span>  
  
     <span data-ttu-id="705b5-112">Wenn Moduleigenschaften bereits für den aktuellen Bereich festgelegt wurden, werden keine Moduleigenschaften importiert.</span><span class="sxs-lookup"><span data-stu-id="705b5-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="705b5-113">Wenn Moduleigenschaften nicht im aktuellen Bereich festgelegt haben, werden sie jedoch importiert nur einmal auf, wenn sie zuerst erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="705b5-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="705b5-114">Wenn diese Moduleigenschaften erneut auftreten, sind sie Duplikate.</span><span class="sxs-lookup"><span data-stu-id="705b5-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="705b5-115">Wenn die Werte aller Module-Eigenschaften (außer MVID) verglichen werden und keine Duplikate gefunden werden, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="705b5-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>  
  
-   <span data-ttu-id="705b5-116">Bei Typdefinitionen (`TypeDef`), also keine Duplikate in den aktuellen Bereich zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="705b5-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="705b5-117">`TypeDef`Objekte werden für alle Duplikate überprüft *vollständig qualifizierter Objektname* + *GUID* + *Versionsnummer*.</span><span class="sxs-lookup"><span data-stu-id="705b5-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="705b5-118">Wenn eine auf Namen oder die GUID Übereinstimmung und keines der anderen beiden Elemente unterscheidet, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="705b5-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="705b5-119">Andernfalls, wenn alle drei Elemente übereinstimmen, `MergeEnd` ist eine kurze Überprüfung, um sicherzustellen, dass die Einträge in der Tat Duplikate; Wenn nicht, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="705b5-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="705b5-120">Diese kurze Überprüfung gesucht wird:</span><span class="sxs-lookup"><span data-stu-id="705b5-120">This cursory check looks for:</span></span>  
  
    -   <span data-ttu-id="705b5-121">Die gleichen Memberdeklarationen, die in der gleichen Reihenfolge auftreten.</span><span class="sxs-lookup"><span data-stu-id="705b5-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="705b5-122">Elemente, die als gekennzeichneten `mdPrivateScope` (finden Sie unter der [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) Enumeration) sind nicht in diese namensüberprüfung enthalten sie speziell zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="705b5-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>  
  
    -   <span data-ttu-id="705b5-123">Die gleiche Klassenlayout.</span><span class="sxs-lookup"><span data-stu-id="705b5-123">The same class layout.</span></span>  
  
     <span data-ttu-id="705b5-124">Dies bedeutet, dass ein `TypeDef` Objekt muss immer vollständig und konsistent definiert werden in jedem Metadatenbereich in der sie deklariert wird, wenn mehrere Kompilierungseinheiten seine Memberimplementierungen (für eine Klasse) verteilt sind, die vollständige Definition wird davon ausgegangen, dass sein in jedem Bereich vorhanden und nicht inkrementelle für jeden Bereich.</span><span class="sxs-lookup"><span data-stu-id="705b5-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="705b5-125">Z. B. wenn Parameternamen für den Vertrag relevant sind, müssen sie die gleiche Weise wie in jedem Bereich ausgegeben werden. Wenn sie nicht relevant sind, sollten sie nicht in Metadaten ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="705b5-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>  
  
     <span data-ttu-id="705b5-126">Die Ausnahme ist, dass eine `TypeDef` Objekt kann als inkrementelle Member haben `mdPrivateScope`.</span><span class="sxs-lookup"><span data-stu-id="705b5-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="705b5-127">Bei diesen `MergeEnd` inkrementell auf den aktuellen Bereich ohne Berücksichtigung von Duplikaten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="705b5-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="705b5-128">Da der Compiler den privaten Bereich versteht, muss der Compiler verantwortlich zum Erzwingen von Regeln.</span><span class="sxs-lookup"><span data-stu-id="705b5-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>  
  
-   <span data-ttu-id="705b5-129">Relative virtuelle Adresse (RVA) werden nicht importiert oder zusammengeführt werden; der Compiler muss diese Informationen erneut ausgeben.</span><span class="sxs-lookup"><span data-stu-id="705b5-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>  
  
-   <span data-ttu-id="705b5-130">Benutzerdefinierte Attribute werden zusammengeführt, nur, wenn das Element mit dem sie verbunden sind zusammengeführt wird.</span><span class="sxs-lookup"><span data-stu-id="705b5-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="705b5-131">Benutzerdefinierte Attribute einer Klasse zugeordnet werden z. B. zusammengeführt, beim ersten der Klasse auftreten.</span><span class="sxs-lookup"><span data-stu-id="705b5-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="705b5-132">Wenn Sie benutzerdefinierte Attribute zugeordnet sind ein `TypeDef` oder `MemberDef` , der Kompilierungseinheit (z. B. den Zeitstempel, der eine Memberkompilierung) spezifisch ist, werden nicht zusammengeführt, und es liegt im Ermessen des Compilers solche Metadaten entfernen oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="705b5-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="705b5-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="705b5-133">Requirements</span></span>  
 <span data-ttu-id="705b5-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="705b5-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="705b5-135">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="705b5-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="705b5-136">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="705b5-136">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="705b5-137">**.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="705b5-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="705b5-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="705b5-138">See Also</span></span>  
 [<span data-ttu-id="705b5-139">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="705b5-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="705b5-140">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="705b5-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
