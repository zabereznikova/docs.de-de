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
ms.openlocfilehash: 2facc63023a20dd6aaac64d7d036324c31658bc8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501312"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="ccfcd-102">IMetaDataEmit::DefineImportMember-Methode</span><span class="sxs-lookup"><span data-stu-id="ccfcd-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="ccfcd-103">Erstellt einen Verweis auf den angegebenen Member eines Typs oder Moduls, der außerhalb des aktuellen Bereichs definiert ist, und definiert ein Token für diesen Verweis.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccfcd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccfcd-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ccfcd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ccfcd-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="ccfcd-106">in Eine [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) -Schnittstelle, die die Assembly darstellt, aus der der Zielmember importiert wird.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-106">[in] An [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="ccfcd-107">in Ein Array, das den Hash für die durch angegebene Assembly enthält `pAssemImport` .</span><span class="sxs-lookup"><span data-stu-id="ccfcd-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="ccfcd-108">[in] Die Anzahl der Bytes im `pbHashValue`-Array.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="ccfcd-109">in Eine [IMetaDataImport](imetadataimport-interface.md) -Schnittstelle, die den Metadatenbereich darstellt, aus dem der Zielmember importiert wird.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-109">[in] An [IMetaDataImport](imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="ccfcd-110">in Das Metadatentoken, das den Zielmember angibt.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="ccfcd-111">Das Token kann ein `mdMethodDef` (für eine Member-Methode), `mdProperty` (für eine Element Eigenschaft) oder `mdFieldDef` (für ein Element Feld) sein.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="ccfcd-112">in Eine [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) -Schnittstelle, die die Assembly darstellt, in die der Zielmember importiert wird.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-112">[in] An [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="ccfcd-113">in Das- `mdTypeRef` oder- `mdModuleRef` Token für den Typ bzw. das Modul, das den Zielmember besitzt.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="ccfcd-114">vorgenommen Das `mdMemberRef` Token, das im aktuellen Gültigkeitsbereich für den Element Verweis definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccfcd-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ccfcd-115">Remarks</span></span>  
 <span data-ttu-id="ccfcd-116">Die `DefineImportMember` -Methode sucht nach dem durch angegebenen Member, der `mbMember` in einem anderen Bereich definiert ist, der durch angegeben wird, `pImport` und ruft seine Eigenschaften ab.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="ccfcd-117">Diese Informationen werden verwendet, um die [IMetaDataEmit::D efinemembership Ref](imetadataemit-definememberref-method.md) -Methode im aktuellen Bereich aufzurufen, um den Element Verweis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="ccfcd-118">Im Allgemeinen müssen Sie vor der Verwendung der `DefineImportMember` -Methode im aktuellen Bereich einen Typverweis oder Modul Verweis für die übergeordnete Klasse, Schnittstelle oder das Modul des Zielmembers erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="ccfcd-119">Das Metadatentoken für diesen Verweis wird dann im-Argument weitergegeben `tkParent` .</span><span class="sxs-lookup"><span data-stu-id="ccfcd-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="ccfcd-120">Sie müssen keinen Verweis auf das übergeordnete Element des Zielmembers erstellen, wenn es später durch den Compiler oder den Linker aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="ccfcd-121">Zusammenfassung:</span><span class="sxs-lookup"><span data-stu-id="ccfcd-121">To summarize:</span></span>  
  
- <span data-ttu-id="ccfcd-122">Wenn das Zielmember ein Feld oder eine Methode ist, verwenden Sie entweder die [IMetaDataEmit::D efinetyperefbyname](imetadataemit-definetyperefbyname-method.md) -Methode oder die [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md) -Methode, um im aktuellen Bereich einen Typverweis für die übergeordnete Klasse oder übergeordnete Schnittstelle des Elements zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="ccfcd-123">Wenn das Zielmember eine globale Variable oder globale Funktion (d. h. kein Member einer Klasse oder Schnittstelle) ist, verwenden Sie die [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md) -Methode, um einen Modul Verweis im aktuellen Bereich für das übergeordnete Modul des Elements zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="ccfcd-124">Wenn das übergeordnete Element des Zielmembers später durch den Compiler oder den Linker aufgelöst wird, übergeben Sie `mdTokenNil` `tkParent` .</span><span class="sxs-lookup"><span data-stu-id="ccfcd-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="ccfcd-125">Das einzige Szenario, in dem dies zutrifft, ist, wenn eine globale Funktion oder globale Variable aus einer OBJ-Datei importiert wird, die letztendlich mit dem aktuellen Modul und den zusammengeführten Metadaten verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccfcd-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ccfcd-126">Requirements</span></span>  
 <span data-ttu-id="ccfcd-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccfcd-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccfcd-128">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ccfcd-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccfcd-129">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccfcd-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccfcd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfcd-131">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="ccfcd-131">See also</span></span>

- [<span data-ttu-id="ccfcd-132">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccfcd-132">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ccfcd-133">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccfcd-133">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
