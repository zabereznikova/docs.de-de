---
title: IMetaDataEmit::DefineImportMember-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175862"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="a2d46-102">IMetaDataEmit::DefineImportMember-Methode</span><span class="sxs-lookup"><span data-stu-id="a2d46-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="a2d46-103">Erstellt einen Verweis auf den angegebenen Member eines Typs oder Moduls, der außerhalb des aktuellen Bereichs definiert ist, und definiert ein Token für diesen Verweis.</span><span class="sxs-lookup"><span data-stu-id="a2d46-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2d46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2d46-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="a2d46-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2d46-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="a2d46-106">[in] Eine [IMetaDataAssemblyImport-Schnittstelle,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) die die Assembly darstellt, aus der das Zielelement importiert wird.</span><span class="sxs-lookup"><span data-stu-id="a2d46-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="a2d46-107">[in] Ein Array, das den Hash `pAssemImport`für die assembly enthält, die von angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a2d46-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="a2d46-108">[in] Die Anzahl der Bytes im `pbHashValue`-Array.</span><span class="sxs-lookup"><span data-stu-id="a2d46-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="a2d46-109">[in] Eine [IMetaDataImport-Schnittstelle,](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) die den Metadatenbereich darstellt, aus dem das Zielmitglied importiert wird.</span><span class="sxs-lookup"><span data-stu-id="a2d46-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="a2d46-110">[in] Das Metadatentoken, das den Zielmember angibt.</span><span class="sxs-lookup"><span data-stu-id="a2d46-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="a2d46-111">Das Token kann `mdMethodDef` ein (für `mdProperty` eine Membermethode), (für eine Membereigenschaft) oder `mdFieldDef` (für ein Memberfeld) Token sein.</span><span class="sxs-lookup"><span data-stu-id="a2d46-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="a2d46-112">[in] Eine [IMetaDataAssemblyEmit-Schnittstelle,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) die die Assembly darstellt, in die das Zielelement importiert wird.</span><span class="sxs-lookup"><span data-stu-id="a2d46-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="a2d46-113">[in] Das `mdTypeRef` `mdModuleRef` oder-Token für den Typ bzw. das Modul, dem bzw. dem das Zielelement gehört.</span><span class="sxs-lookup"><span data-stu-id="a2d46-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="a2d46-114">[out] Das `mdMemberRef` Token, das im aktuellen Bereich für den Memberverweis definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a2d46-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2d46-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a2d46-115">Remarks</span></span>  
 <span data-ttu-id="a2d46-116">Die `DefineImportMember` Methode sucht den Member, der durch `mbMember`angegeben wird, `pImport`der in einem anderen Bereich definiert ist, von angegeben und ruft seine Eigenschaften ab.</span><span class="sxs-lookup"><span data-stu-id="a2d46-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="a2d46-117">Es verwendet diese Informationen, um die [IMetaDataEmit::DefineMemberRef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) im aktuellen Bereich aufzurufen, um den Memberverweis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2d46-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="a2d46-118">Im Allgemeinen müssen `DefineImportMember` Sie vor der Verwendung der Methode im aktuellen Bereich eine Typreferenz oder Modulreferenz für die übergeordnete Klasse, Schnittstelle oder das Modul des Zielmembers erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2d46-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="a2d46-119">Das Metadatentoken für diesen Verweis `tkParent` wird dann im Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="a2d46-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="a2d46-120">Sie müssen keinen Verweis auf das übergeordnete Element des Zielmembers erstellen, wenn er später vom Compiler oder Linker aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a2d46-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="a2d46-121">Zusammenfassung:</span><span class="sxs-lookup"><span data-stu-id="a2d46-121">To summarize:</span></span>  
  
- <span data-ttu-id="a2d46-122">Wenn es sich bei dem Zielmember um ein Feld oder eine Methode handelt, verwenden Sie entweder die [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) oder die [IMetaDataEmit::DefineImportType-Methode,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) um im aktuellen Bereich einen Typverweis für die übergeordnete Klasse oder übergeordnete Schnittstelle des Elements zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2d46-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="a2d46-123">Wenn es sich bei dem Zielelement um eine globale Variable oder globale Funktion (d. h. kein Member einer Klasse oder Schnittstelle) handelt, verwenden Sie die [IMetaDataEmit::DefineModuleRef-Methode,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) um im aktuellen Bereich einen Modulverweis für das übergeordnete Modul des Elements zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2d46-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="a2d46-124">Wenn das übergeordnete Element des Zielmembers später vom Compiler oder `mdTokenNil` `tkParent`Linker aufgelöst wird, geben Sie .</span><span class="sxs-lookup"><span data-stu-id="a2d46-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="a2d46-125">Das einzige Szenario, in dem dies zutrifft, ist, wenn eine globale Funktion oder globale Variable aus einer .obj-Datei importiert wird, die letztendlich mit dem aktuellen Modul verknüpft und die Metadaten zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a2d46-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2d46-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a2d46-126">Requirements</span></span>  
 <span data-ttu-id="a2d46-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2d46-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2d46-128">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a2d46-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2d46-129">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a2d46-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2d46-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2d46-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d46-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2d46-131">See also</span></span>

- [<span data-ttu-id="a2d46-132">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2d46-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a2d46-133">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2d46-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
