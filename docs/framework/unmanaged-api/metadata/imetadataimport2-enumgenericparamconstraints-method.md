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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cdc617039ac8328e0153abc7cc3752c54060a8c4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481464"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="98d6c-102">IMetaDataImport2::EnumGenericParamConstraints-Methode</span><span class="sxs-lookup"><span data-stu-id="98d6c-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="98d6c-103">Ruft einen Enumerator für ein Array von generischen Parameter-Einschränkungen, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="98d6c-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98d6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98d6c-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98d6c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="98d6c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="98d6c-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="98d6c-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="98d6c-107">[in]   Ein Token, das den generischen Parameter darstellt, deren Einschränkungen aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="98d6c-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="98d6c-108">[out] Das Array von Einschränkungen für generische Typparameter aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="98d6c-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="98d6c-109">[in]   Die angeforderte maximale Anzahl von Token in platzieren `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="98d6c-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="98d6c-110">[out] Ein Zeiger auf die Anzahl der Token in platziert `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="98d6c-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98d6c-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="98d6c-111">Return Value</span></span>  
  
|<span data-ttu-id="98d6c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98d6c-112">HRESULT</span></span>|<span data-ttu-id="98d6c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98d6c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="98d6c-114">`EnumGenericParameterConstraints` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="98d6c-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="98d6c-115">`phEnum` enthält keine Memberelemente.</span><span class="sxs-lookup"><span data-stu-id="98d6c-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="98d6c-116">In diesem Fall `pcGenericParameterConstraints` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="98d6c-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98d6c-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="98d6c-117">Requirements</span></span>  
 <span data-ttu-id="98d6c-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98d6c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98d6c-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="98d6c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98d6c-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="98d6c-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98d6c-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98d6c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d6c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98d6c-122">See also</span></span>
- [<span data-ttu-id="98d6c-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98d6c-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="98d6c-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98d6c-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
