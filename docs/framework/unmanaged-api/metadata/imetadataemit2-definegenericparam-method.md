---
title: IMetaDataEmit2::DefineGenericParam-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de8547ed0ee83bafe4612bdcd62607fc94fb3f69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163721"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="2bb8d-102">IMetaDataEmit2::DefineGenericParam-Methode</span><span class="sxs-lookup"><span data-stu-id="2bb8d-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="2bb8d-103">Erstellt eine Definition für einen generischen Typparameter, und ruft ein Token an den generischen Typparameter ab.</span><span class="sxs-lookup"><span data-stu-id="2bb8d-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb8d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bb8d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2bb8d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2bb8d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="2bb8d-106">[in] Ein `mdTypeDef` oder `mdMethodDef` Token, das die Methode oder der Konstruktor für das Definieren eines generischen Parameters darstellt.</span><span class="sxs-lookup"><span data-stu-id="2bb8d-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="2bb8d-107">[in] Der Index des generischen Parameters.</span><span class="sxs-lookup"><span data-stu-id="2bb8d-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="2bb8d-108">[in] Der Wert der [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) -Enumeration, der den Typ für den generischen Parameter beschreibt.</span><span class="sxs-lookup"><span data-stu-id="2bb8d-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="2bb8d-109">[in] Der Name des Parameters.</span><span class="sxs-lookup"><span data-stu-id="2bb8d-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="2bb8d-110">[in] Dieser Parameter ist für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="2bb8d-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="2bb8d-111">[in] Ein NULL-terminierte Array von Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="2bb8d-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="2bb8d-112">Arraymember muss ein `mdTypeDef`, `mdTypeRef`, oder `mdTypeSpec` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="2bb8d-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="2bb8d-113">[out] Ein Token, das den generischen Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="2bb8d-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bb8d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2bb8d-114">Requirements</span></span>  
 <span data-ttu-id="2bb8d-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bb8d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bb8d-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2bb8d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bb8d-117">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2bb8d-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="2bb8d-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2bb8d-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2bb8d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bb8d-119">See also</span></span>

- [<span data-ttu-id="2bb8d-120">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2bb8d-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2bb8d-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2bb8d-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
