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
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175810"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="07ea7-102">IMetaDataEmit::DefineNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="07ea7-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="07ea7-103">Erstellt die Metadatensignatur einer Typdefinition, gibt ein `mdTypeDef` Token für diesen Typ zurück und gibt an, `tdEncloser` dass der definierte Typ ein Member des Typs ist, auf den der Parameter verweist.</span><span class="sxs-lookup"><span data-stu-id="07ea7-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ea7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07ea7-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07ea7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07ea7-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="07ea7-106">[in] Der Name des Typs in Unicode.</span><span class="sxs-lookup"><span data-stu-id="07ea7-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="07ea7-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="07ea7-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="07ea7-108">Dies ist eine `CorTypeAttr` Bitmaske von Werten.</span><span class="sxs-lookup"><span data-stu-id="07ea7-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="07ea7-109">[in] Das Token der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="07ea7-109">[in] The token of the base class.</span></span> <span data-ttu-id="07ea7-110">Dies ist `mdTypeDef` entweder `mdTypeRef` ein oder ein Token.</span><span class="sxs-lookup"><span data-stu-id="07ea7-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="07ea7-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="07ea7-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="07ea7-112">[in] Ein Array von Token, die die Schnittstellen angeben, die diese Klasse oder Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="07ea7-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="07ea7-113">[in] Das Token des einschließenden Typs.</span><span class="sxs-lookup"><span data-stu-id="07ea7-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="07ea7-114">Das letzte Element des `mdTokenNil`Arrays muss .</span><span class="sxs-lookup"><span data-stu-id="07ea7-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="07ea7-115">[out] Das `mdTypeDef` token zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="07ea7-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07ea7-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="07ea7-116">Requirements</span></span>  
 <span data-ttu-id="07ea7-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07ea7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07ea7-118">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="07ea7-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07ea7-119">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="07ea7-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07ea7-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07ea7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ea7-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07ea7-121">See also</span></span>

- [<span data-ttu-id="07ea7-122">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07ea7-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="07ea7-123">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07ea7-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
