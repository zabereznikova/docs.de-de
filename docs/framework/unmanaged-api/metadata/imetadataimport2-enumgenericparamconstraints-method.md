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
ms.openlocfilehash: fd5d35cb13bb55fc73e160089cbc1050cb3d5c0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449217"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="39c9e-102">IMetaDataImport2::EnumGenericParamConstraints-Methode</span><span class="sxs-lookup"><span data-stu-id="39c9e-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="39c9e-103">Ruft einen Enumerator für ein Array mit Einschränkungen für generische Typparameter durch das angegebene Token dargestellten generischen Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="39c9e-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39c9e-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39c9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="39c9e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="39c9e-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="39c9e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="39c9e-107">[in]   Ein Token, das den generischen Parameter darstellt, deren Einschränkungen aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="39c9e-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="39c9e-108">[out] Das Array von Einschränkungen für generische Typparameter aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="39c9e-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="39c9e-109">[in]   Die angeforderte maximale Anzahl von Token zu versehen `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="39c9e-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="39c9e-110">[out] Ein Zeiger auf die Anzahl der Token in platziert `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="39c9e-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39c9e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="39c9e-111">Return Value</span></span>  
  
|<span data-ttu-id="39c9e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39c9e-112">HRESULT</span></span>|<span data-ttu-id="39c9e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39c9e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="39c9e-114">`EnumGenericParameterConstraints` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="39c9e-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="39c9e-115">`phEnum` verfügt über keine Memberelemente.</span><span class="sxs-lookup"><span data-stu-id="39c9e-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="39c9e-116">In diesem Fall `pcGenericParameterConstraints` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="39c9e-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="39c9e-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="39c9e-117">Requirements</span></span>  
 <span data-ttu-id="39c9e-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39c9e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39c9e-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="39c9e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39c9e-120">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="39c9e-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39c9e-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39c9e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c9e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39c9e-122">See Also</span></span>  
 [<span data-ttu-id="39c9e-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39c9e-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="39c9e-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39c9e-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
