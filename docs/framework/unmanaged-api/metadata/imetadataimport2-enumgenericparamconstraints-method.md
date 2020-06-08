---
title: IMetaDataImport2::EnumGenericParamConstraints-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
ms.openlocfilehash: af226f9317b67b23e03d06614ed5b9c956939c22
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503418"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="26cc8-102">IMetaDataImport2::EnumGenericParamConstraints-Methode</span><span class="sxs-lookup"><span data-stu-id="26cc8-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="26cc8-103">Ruft einen Enumerator für ein Array von generischen Parameter Einschränkungen ab, die dem generischen Parameter zugeordnet sind, der durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="26cc8-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26cc8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26cc8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26cc8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="26cc8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="26cc8-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="26cc8-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="26cc8-107">in   Ein Token, das den generischen Parameter darstellt, dessen Einschränkungen aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="26cc8-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="26cc8-108">vorgenommen Das Array der zu enumerieren generischen Parameter Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="26cc8-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="26cc8-109">in   Die angeforderte maximale Anzahl von Token, die in platziert werden sollen `rGenericParamConstraints` .</span><span class="sxs-lookup"><span data-stu-id="26cc8-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="26cc8-110">vorgenommen Ein Zeiger auf die Anzahl von Token, die in platziert werden `rGenericParamConstraints` .</span><span class="sxs-lookup"><span data-stu-id="26cc8-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26cc8-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="26cc8-111">Return Value</span></span>  
  
|<span data-ttu-id="26cc8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="26cc8-112">HRESULT</span></span>|<span data-ttu-id="26cc8-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="26cc8-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="26cc8-114">`EnumGenericParameterConstraints`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="26cc8-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="26cc8-115">`phEnum`hat keine Member-Elemente.</span><span class="sxs-lookup"><span data-stu-id="26cc8-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="26cc8-116">In diesem Fall `pcGenericParameterConstraints` wird auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="26cc8-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26cc8-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="26cc8-117">Requirements</span></span>  
 <span data-ttu-id="26cc8-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26cc8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26cc8-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="26cc8-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26cc8-120">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="26cc8-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="26cc8-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26cc8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26cc8-122">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="26cc8-122">See also</span></span>

- [<span data-ttu-id="26cc8-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26cc8-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="26cc8-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26cc8-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
