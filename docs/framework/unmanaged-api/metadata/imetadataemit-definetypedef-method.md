---
title: IMetaDataEmit::DefineTypeDef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175758"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="b9409-102">IMetaDataEmit::DefineTypeDef-Methode</span><span class="sxs-lookup"><span data-stu-id="b9409-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="b9409-103">Erstellt eine Typdefinition für einen Common Language-Laufzeittyp und ruft ein Metadatentoken für diese Typdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="b9409-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9409-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9409-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9409-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b9409-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="b9409-106">[in] Der Name des Typs in Unicode.</span><span class="sxs-lookup"><span data-stu-id="b9409-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="b9409-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="b9409-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="b9409-108">Dies ist eine `CoreTypeAttr` Bitmaske von Werten.</span><span class="sxs-lookup"><span data-stu-id="b9409-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="b9409-109">[in] Das Token der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="b9409-109">[in] The token of the base class.</span></span> <span data-ttu-id="b9409-110">Es muss entweder `mdTypeDef` ein `mdTypeRef` oder ein Token sein.</span><span class="sxs-lookup"><span data-stu-id="b9409-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="b9409-111">[in] Ein Array von Token, das die Schnittstellen angibt, die diese Klasse oder Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="b9409-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="b9409-112">[out] Das `mdTypeDef` token zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b9409-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9409-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b9409-113">Remarks</span></span>  
 <span data-ttu-id="b9409-114">Ein Flag `dwTypeDefFlags` in gibt an, ob es sich bei dem zu erstellenden Typ um einen allgemeinen Typsystemreferenztyp (Klasse oder Schnittstelle) oder einen allgemeinen Typsystemwerttyp handelt.</span><span class="sxs-lookup"><span data-stu-id="b9409-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="b9409-115">Abhängig von den angegebenen Parametern kann diese Methode als `mdInterfaceImpl` Nebeneffekt auch einen Datensatz für jede Schnittstelle erstellen, die von diesem Typ geerbt oder implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="b9409-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="b9409-116">Diese Methode gibt jedoch keines `mdInterfaceImpl` dieser Token zurück.</span><span class="sxs-lookup"><span data-stu-id="b9409-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="b9409-117">Wenn ein Client später ein `mdInterfaceImpl` Token hinzufügen oder `IMetaDataImport` ändern möchte, muss er die Schnittstelle verwenden, um sie aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="b9409-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="b9409-118">Wenn Sie die COM-Semantik `[default]` der Schnittstelle verwenden möchten, sollten Sie `rtkImplements`die Standardschnittstelle als erstes Element in angeben. Ein benutzerdefiniertes Attribut, das für die Klasse festgelegt ist, gibt an, dass die Klasse über eine Standardschnittstelle verfügt (die immer als das erste `mdInterfaceImpl` für die Klasse deklarierte Token angenommen wird).</span><span class="sxs-lookup"><span data-stu-id="b9409-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="b9409-119">Jedes Element `rtkImplements` des Arrays enthält ein `mdTypeDef` oder `mdTypeRef` ein Token.</span><span class="sxs-lookup"><span data-stu-id="b9409-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="b9409-120">Das letzte Element im `mdTokenNil`Array muss .</span><span class="sxs-lookup"><span data-stu-id="b9409-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9409-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b9409-121">Requirements</span></span>  
 <span data-ttu-id="b9409-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9409-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9409-123">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b9409-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9409-124">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="b9409-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9409-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9409-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9409-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9409-126">See also</span></span>

- [<span data-ttu-id="b9409-127">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9409-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b9409-128">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9409-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
