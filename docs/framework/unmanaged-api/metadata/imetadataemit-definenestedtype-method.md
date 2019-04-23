---
title: IMetaDataEmit::DefineNestedType-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ebd4e9beca315ef8284c915800afec6bdb78c78
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183234"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="cab6d-102">IMetaDataEmit::DefineNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="cab6d-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="cab6d-103">Erstellt die Metadatensignatur einer Typdefinition ist, wird ein `mdTypeDef` ein Sicherheitstoken für diesen Typ, und gibt an, dass der definierte Typ ein Member des Typs verwiesen wird, durch die `tdEncloser` Parameter.</span><span class="sxs-lookup"><span data-stu-id="cab6d-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cab6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cab6d-104">Syntax</span></span>  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cab6d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cab6d-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="cab6d-106">[in] Der Name des Typs im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="cab6d-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="cab6d-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="cab6d-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="cab6d-108">Dies ist eine Bitmaske der `CorTypeAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="cab6d-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="cab6d-109">[in] Das Token der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="cab6d-109">[in] The token of the base class.</span></span> <span data-ttu-id="cab6d-110">Dies ist entweder ein `mdTypeDef` oder `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="cab6d-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="cab6d-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="cab6d-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="cab6d-112">[in] Ein Array von Token, die die Schnittstellen anzugeben, die diese Klasse oder Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="cab6d-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="cab6d-113">[in] Das Token des einschließenden Typs.</span><span class="sxs-lookup"><span data-stu-id="cab6d-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="cab6d-114">Das letzte Element des Arrays muss `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="cab6d-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="cab6d-115">[out] Die `mdTypeDef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="cab6d-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cab6d-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cab6d-116">Requirements</span></span>  
 <span data-ttu-id="cab6d-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cab6d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cab6d-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cab6d-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cab6d-119">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="cab6d-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cab6d-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cab6d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cab6d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cab6d-121">See also</span></span>

- [<span data-ttu-id="cab6d-122">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cab6d-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cab6d-123">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cab6d-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
