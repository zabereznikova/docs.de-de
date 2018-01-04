---
title: IMetaDataEmit::DefineImportMember-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineImportMember
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bbe2c3144372ba66a0b3bad6198aefeeb7e12d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="b51cc-102">IMetaDataEmit::DefineImportMember-Methode</span><span class="sxs-lookup"><span data-stu-id="b51cc-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="b51cc-103">Erstellt einen Verweis auf das angegebene Element von einem Typ oder Modul, die außerhalb des aktuellen Bereichs definiert ist, und ein Token für diesen Verweis definiert.</span><span class="sxs-lookup"><span data-stu-id="b51cc-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b51cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b51cc-104">Syntax</span></span>  
  
```  
HRESULT DefineImportMember (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,   
    [in]  mdToken                  mbMember,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [in]  mdToken                  tkParent,   
    [out] mdMemberRef              *pmr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b51cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b51cc-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="b51cc-106">[in] Ein [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle, die die Assembly darstellt, aus dem der Zielmember importiert wird.</span><span class="sxs-lookup"><span data-stu-id="b51cc-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="b51cc-107">[in] Ein Array, das den Hash für die Assembly gemäß enthält `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="b51cc-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="b51cc-108">[in] Die Anzahl der Bytes im `pbHashValue`-Array.</span><span class="sxs-lookup"><span data-stu-id="b51cc-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="b51cc-109">[in] Ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle, die den Metadatenbereich darstellt, aus dem der Zielmember importiert wird.</span><span class="sxs-lookup"><span data-stu-id="b51cc-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="b51cc-110">[in] Das Metadatentoken, das das Ziel-Element angibt.</span><span class="sxs-lookup"><span data-stu-id="b51cc-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="b51cc-111">Das Token kann ein `mdMethodDef` (für eine Membermethode) `mdProperty` (für eine Elementeigenschaft) oder `mdFieldDef` (für ein Memberfeld) token.</span><span class="sxs-lookup"><span data-stu-id="b51cc-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="b51cc-112">[in] Ein [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) Schnittstelle, die die Assembly darstellt, in dem der Zielmember importiert wird.</span><span class="sxs-lookup"><span data-stu-id="b51cc-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="b51cc-113">[in] Die `mdTypeRef` oder `mdModuleRef` token für den Typ oder Modul, bzw. der Besitzer ist des Zielelements.</span><span class="sxs-lookup"><span data-stu-id="b51cc-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="b51cc-114">[out] Die `mdMemberRef` Token, das im aktuellen Bereich für den Parameterverweis definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b51cc-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b51cc-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b51cc-115">Remarks</span></span>  
 <span data-ttu-id="b51cc-116">Die `DefineImportMember` Methode sucht das Element, angegeben durch `mbMember`, d. h. in einem anderen Bereich von angegebenen definiert `pImport`, und ruft dessen Eigenschaften ab.</span><span class="sxs-lookup"><span data-stu-id="b51cc-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="b51cc-117">Er verwendet diese Informationen zum Aufrufen der [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) -Methode im aktuellen Bereich für den Parameterverweis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b51cc-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="b51cc-118">Im Allgemeinen vor dem Verwenden der `DefineImportMember` -Methode, Sie müssen erstellen, in den aktuellen Bereich, einen Typverweis oder Modulverweis für die übergeordnete Klasse, Schnittstelle oder Modul des Zielelements.</span><span class="sxs-lookup"><span data-stu-id="b51cc-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="b51cc-119">Das Metadatentoken für diesen Verweis dann übergeben der `tkParent` Argument.</span><span class="sxs-lookup"><span data-stu-id="b51cc-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="b51cc-120">Sie müssen sich nicht, erstellen einen Verweis auf das Ziel Element übergeordneten Elements aus, wenn sie später vom Compiler oder Linker aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b51cc-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="b51cc-121">Zusammenfassung:</span><span class="sxs-lookup"><span data-stu-id="b51cc-121">To summarize:</span></span>  
  
-   <span data-ttu-id="b51cc-122">Das Target-Element ein Feld oder eine Methode ist, verwenden Sie entweder die [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) oder [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) Methode zum Erstellen der eines Typverweis, im aktuellen Bereich für die übergeordnete Klasse oder Schnittstelle des Elements.</span><span class="sxs-lookup"><span data-stu-id="b51cc-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
-   <span data-ttu-id="b51cc-123">Wenn der Zielmember eine globale Variable oder Funktion (d. h., kein Mitglied einer Klasse oder Schnittstelle) ist, verwenden die [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) Methode zum Erstellen eines Modulverweis des aktuellen Bereichs seines übergeordneten Elements Modul.</span><span class="sxs-lookup"><span data-stu-id="b51cc-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
-   <span data-ttu-id="b51cc-124">Wenn der Zielmember übergeordneten später vom Compiler oder Linker aufgelöst wird, übergeben Sie `mdTokenNil` in `tkParent`.</span><span class="sxs-lookup"><span data-stu-id="b51cc-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="b51cc-125">Ist das einzige Szenario, in dem dies gilt, eine globale Funktion oder globale Variable aus einer OBJ-Datei, die letztendlich in das aktuelle Modul verknüpft, importiert wird und die Metadaten zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="b51cc-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b51cc-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b51cc-126">Requirements</span></span>  
 <span data-ttu-id="b51cc-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b51cc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b51cc-128">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b51cc-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b51cc-129">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="b51cc-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b51cc-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b51cc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51cc-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b51cc-131">See Also</span></span>  
 [<span data-ttu-id="b51cc-132">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b51cc-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b51cc-133">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b51cc-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
