---
title: IMetaDataEmit::DefineNestedType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineNestedType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf0357275b0ad2dd7d57a3b3f07e17dc3e38e1a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="90740-102">IMetaDataEmit::DefineNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="90740-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="90740-103">Erstellt die Metadatensignatur einer Typdefinition ist, wird ein `mdTypeDef` token für diesen Typ und gibt an, dass der definierte Typ ein Member des Typs verweist die `tdEncloser` Parameter.</span><span class="sxs-lookup"><span data-stu-id="90740-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90740-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90740-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="90740-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90740-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="90740-106">[in] Der Name des Typs im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="90740-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="90740-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="90740-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="90740-108">Dies ist eine Bitmaske der `CorTypeAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="90740-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="90740-109">[in] Das Token der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="90740-109">[in] The token of the base class.</span></span> <span data-ttu-id="90740-110">Dies liegt entweder an einem `mdTypeDef` oder ein `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="90740-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="90740-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="90740-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="90740-112">[in] Ein Array von Token, die die Schnittstellen anzugeben, die diese Klasse oder Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="90740-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="90740-113">[in] Das Token des einschließenden Typs.</span><span class="sxs-lookup"><span data-stu-id="90740-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="90740-114">Das letzte Element des Arrays muss `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="90740-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="90740-115">[out] Die `mdTypeDef` Token zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="90740-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90740-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90740-116">Requirements</span></span>  
 <span data-ttu-id="90740-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90740-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90740-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90740-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90740-119">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="90740-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90740-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90740-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90740-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90740-121">See Also</span></span>  
 [<span data-ttu-id="90740-122">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90740-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="90740-123">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90740-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
