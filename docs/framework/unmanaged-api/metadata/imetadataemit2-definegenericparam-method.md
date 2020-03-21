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
ms.openlocfilehash: 1868d13a9dbb73dbdf64e49c395bdbff02ce89d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177452"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="e1d68-102">IMetaDataEmit2::DefineGenericParam-Methode</span><span class="sxs-lookup"><span data-stu-id="e1d68-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="e1d68-103">Erstellt eine Definition für einen generischen Typparameter und ruft ein Token für diesen generischen Typparameter ab.</span><span class="sxs-lookup"><span data-stu-id="e1d68-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1d68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1d68-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="e1d68-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e1d68-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e1d68-106">[in] Ein `mdTypeDef` `mdMethodDef` oder ein Token, das die Methode oder den Konstruktor darstellt, für die ein generischer Parameter definiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1d68-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="e1d68-107">[in] Der Index des generischen Parameters.</span><span class="sxs-lookup"><span data-stu-id="e1d68-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="e1d68-108">[in] Ein Wert der [CorGenericParamAttr-Enumeration,](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) der den Typ für den generischen Parameter beschreibt.</span><span class="sxs-lookup"><span data-stu-id="e1d68-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="e1d68-109">[in] Der Name des Parameters.</span><span class="sxs-lookup"><span data-stu-id="e1d68-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="e1d68-110">[in] Dieser Parameter ist für zukünftige Erweiterbarkeit reserviert.</span><span class="sxs-lookup"><span data-stu-id="e1d68-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="e1d68-111">[in] Ein Null-Termin-Array von Typeinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="e1d68-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="e1d68-112">Arraymember müssen `mdTypeDef`ein `mdTypeRef`, `mdTypeSpec` oder Metadatentoken sein.</span><span class="sxs-lookup"><span data-stu-id="e1d68-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="e1d68-113">[out] Ein Token, das den generischen Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="e1d68-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1d68-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e1d68-114">Requirements</span></span>  
 <span data-ttu-id="e1d68-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1d68-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1d68-116">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e1d68-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1d68-117">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e1d68-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e1d68-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1d68-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d68-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1d68-119">See also</span></span>

- [<span data-ttu-id="e1d68-120">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1d68-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="e1d68-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1d68-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
