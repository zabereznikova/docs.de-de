---
title: IMetaDataEmit2::DefineGenericParam-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 598c616ca91b73d9cb184d9e431e75d00d3f9850
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="a3532-102">IMetaDataEmit2::DefineGenericParam-Methode</span><span class="sxs-lookup"><span data-stu-id="a3532-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="a3532-103">Erstellt eine Definition für einen generischen Typparameter, und ruft ein Token an den generischen Typparameter ab.</span><span class="sxs-lookup"><span data-stu-id="a3532-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3532-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3532-104">Syntax</span></span>  
  
```  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3532-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3532-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a3532-106">[in] Ein `mdTypeDef` oder `mdMethodDef` Token, das die Methode oder der Konstruktor für die Definition eines generischen Parameters darstellt.</span><span class="sxs-lookup"><span data-stu-id="a3532-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="a3532-107">[in] Der Index des generischen Parameters.</span><span class="sxs-lookup"><span data-stu-id="a3532-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="a3532-108">[in] Der Wert der [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) -Enumeration, der den Typ für den generischen Parameter beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a3532-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="a3532-109">[in] Der Name des Parameters.</span><span class="sxs-lookup"><span data-stu-id="a3532-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="a3532-110">[in] Dieser Parameter ist für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="a3532-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="a3532-111">[in] Ein Null endendes Array von typeinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="a3532-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="a3532-112">Arraymember muss ein `mdTypeDef`, `mdTypeRef`, oder `mdTypeSpec` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="a3532-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="a3532-113">[out] Ein Token, das den generischen Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="a3532-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3532-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3532-114">Requirements</span></span>  
 <span data-ttu-id="a3532-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3532-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3532-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a3532-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3532-117">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a3532-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3532-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3532-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3532-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3532-119">See Also</span></span>  
 [<span data-ttu-id="a3532-120">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3532-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="a3532-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3532-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
