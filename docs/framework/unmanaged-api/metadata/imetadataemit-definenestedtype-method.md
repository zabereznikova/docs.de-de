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
ms.openlocfilehash: 2b24c2ca6907dfdb63ad934ec30557c246db174c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004354"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="8b968-102">IMetaDataEmit::DefineNestedType-Methode</span><span class="sxs-lookup"><span data-stu-id="8b968-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="8b968-103">Erstellt die Metadatensignatur einer Typdefinition, gibt ein `mdTypeDef` Token für diesen Typ zurück und gibt an, dass der definierte Typ ein Member des Typs ist, auf den vom-Parameter verwiesen wird `tdEncloser` .</span><span class="sxs-lookup"><span data-stu-id="8b968-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b968-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b968-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8b968-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b968-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="8b968-106">in Der Name des Typs in Unicode.</span><span class="sxs-lookup"><span data-stu-id="8b968-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="8b968-107">[in] `TypeDef` legt.</span><span class="sxs-lookup"><span data-stu-id="8b968-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="8b968-108">Dies ist eine Bitmaske von `CorTypeAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="8b968-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="8b968-109">in Das Token der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="8b968-109">[in] The token of the base class.</span></span> <span data-ttu-id="8b968-110">Dabei handelt es sich entweder um ein- `mdTypeDef` oder- `mdTypeRef` Token.</span><span class="sxs-lookup"><span data-stu-id="8b968-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="8b968-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="8b968-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="8b968-112">in Ein Array von Token, die die Schnittstellen angeben, die von dieser Klasse oder Schnittstelle implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="8b968-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="8b968-113">in Das Token des einschließenden Typs.</span><span class="sxs-lookup"><span data-stu-id="8b968-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="8b968-114">Das letzte Element des Arrays muss sein `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="8b968-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="8b968-115">vorgenommen Das `mdTypeDef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="8b968-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b968-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8b968-116">Requirements</span></span>  
 <span data-ttu-id="8b968-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b968-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b968-118">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8b968-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b968-119">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="8b968-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b968-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b968-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b968-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b968-121">See also</span></span>

- [<span data-ttu-id="8b968-122">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b968-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8b968-123">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b968-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
