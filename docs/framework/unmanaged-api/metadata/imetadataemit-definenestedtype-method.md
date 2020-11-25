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
ms.openlocfilehash: 99dc141cca0f911c8dd65645f6c22d950cc678d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719540"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="42dce-102">IMetaDataEmit::DefineNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="42dce-102">IMetaDataEmit::DefineNestedType Method</span></span>

<span data-ttu-id="42dce-103">Erstellt die Metadatensignatur einer Typdefinition, gibt ein `mdTypeDef` Token für diesen Typ zurück und gibt an, dass der definierte Typ ein Member des Typs ist, auf den vom-Parameter verwiesen wird `tdEncloser` .</span><span class="sxs-lookup"><span data-stu-id="42dce-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42dce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42dce-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="42dce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="42dce-105">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="42dce-106">in Der Name des Typs in Unicode.</span><span class="sxs-lookup"><span data-stu-id="42dce-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="42dce-107">[in] `TypeDef` legt.</span><span class="sxs-lookup"><span data-stu-id="42dce-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="42dce-108">Dies ist eine Bitmaske von `CorTypeAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="42dce-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="42dce-109">in Das Token der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="42dce-109">[in] The token of the base class.</span></span> <span data-ttu-id="42dce-110">Dabei handelt es sich entweder um ein- `mdTypeDef` oder- `mdTypeRef` Token.</span><span class="sxs-lookup"><span data-stu-id="42dce-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="42dce-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="42dce-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="42dce-112">in Ein Array von Token, die die Schnittstellen angeben, die von dieser Klasse oder Schnittstelle implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="42dce-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="42dce-113">in Das Token des einschließenden Typs.</span><span class="sxs-lookup"><span data-stu-id="42dce-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="42dce-114">Das letzte Element des Arrays muss sein `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="42dce-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="42dce-115">vorgenommen Das `mdTypeDef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="42dce-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42dce-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="42dce-116">Requirements</span></span>  

 <span data-ttu-id="42dce-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42dce-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42dce-118">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="42dce-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42dce-119">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="42dce-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42dce-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42dce-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42dce-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42dce-121">See also</span></span>

- [<span data-ttu-id="42dce-122">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42dce-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="42dce-123">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42dce-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
