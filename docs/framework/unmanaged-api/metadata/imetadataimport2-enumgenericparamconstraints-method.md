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
ms.openlocfilehash: f66b0145dbaece7292d2ccad169a97fbb10b6d11
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186680"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="9376b-102">IMetaDataImport2::EnumGenericParamConstraints-Methode</span><span class="sxs-lookup"><span data-stu-id="9376b-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="9376b-103">Ruft einen Enumerator für ein Array von generischen Parameter-Einschränkungen, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9376b-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9376b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9376b-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9376b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9376b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9376b-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="9376b-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="9376b-107">[in]   Ein Token, das den generischen Parameter darstellt, deren Einschränkungen aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9376b-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="9376b-108">[out] Das Array von Einschränkungen für generische Typparameter aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="9376b-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9376b-109">[in]   Die angeforderte maximale Anzahl von Token in platzieren `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="9376b-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="9376b-110">[out] Ein Zeiger auf die Anzahl der Token in platziert `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="9376b-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9376b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9376b-111">Return Value</span></span>  
  
|<span data-ttu-id="9376b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9376b-112">HRESULT</span></span>|<span data-ttu-id="9376b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9376b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParameterConstraints` <span data-ttu-id="9376b-114">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9376b-114">returned successfully.</span></span>|  
|`S_FALSE`|`phEnum` <span data-ttu-id="9376b-115">enthält keine Memberelemente.</span><span class="sxs-lookup"><span data-stu-id="9376b-115">has no member elements.</span></span> <span data-ttu-id="9376b-116">In diesem Fall `pcGenericParameterConstraints` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9376b-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9376b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9376b-117">Requirements</span></span>  
 <span data-ttu-id="9376b-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9376b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9376b-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9376b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9376b-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9376b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="9376b-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="9376b-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9376b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9376b-122">See also</span></span>

- [<span data-ttu-id="9376b-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9376b-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="9376b-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9376b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
