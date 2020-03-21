---
title: IMetaDataImport2::EnumGenericParams-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
ms.openlocfilehash: 55709e79cd8bdb36fe1e32ee8a699fccb1b1bbc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175303"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="5d044-102">IMetaDataImport2::EnumGenericParams-Methode</span><span class="sxs-lookup"><span data-stu-id="5d044-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="5d044-103">Ruft einen Enumerator für ein Array generischer Parametertoken ab, die dem angegebenen TypeDef- oder MethodDef-Token zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5d044-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d044-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d044-104">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d044-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d044-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5d044-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="5d044-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="5d044-107">[in] Das TypeDef- oder MethodDef-Token, dessen generische Parameter aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5d044-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="5d044-108">[out] Das Array generischer Parameter, die aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5d044-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5d044-109">[in] Die angeforderte maximale Anzahl von `rGenericParams`Token, die in platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5d044-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="5d044-110">[out] Die zurückgegebene Anzahl von `rGenericParams`Token, die in platziert wurden.</span><span class="sxs-lookup"><span data-stu-id="5d044-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d044-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d044-111">Return Value</span></span>  
  
|<span data-ttu-id="5d044-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d044-112">HRESULT</span></span>|<span data-ttu-id="5d044-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d044-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5d044-114">`EnumGenericParams`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5d044-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5d044-115">`phEnum`hat keine Elementelemente.</span><span class="sxs-lookup"><span data-stu-id="5d044-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="5d044-116">In diesem `pcGenericParams` Fall ist auf 0 (Null) gesetzt.</span><span class="sxs-lookup"><span data-stu-id="5d044-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d044-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5d044-117">Requirements</span></span>  
 <span data-ttu-id="5d044-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d044-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d044-119">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5d044-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d044-120">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5d044-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d044-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d044-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d044-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d044-122">See also</span></span>

- [<span data-ttu-id="5d044-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d044-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="5d044-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d044-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
