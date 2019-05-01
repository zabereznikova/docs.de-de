---
title: IMetaDataImport::EnumProperties-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 410fd7a702d3aa3812b4ea053c43fdaa507a474a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042509"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="5059f-102">IMetaDataImport::EnumProperties-Methode</span><span class="sxs-lookup"><span data-stu-id="5059f-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="5059f-103">Zählt PropertyDef-Token auf, die die Eigenschaften des Typs darstellen, auf den vom angegebenen TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5059f-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5059f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5059f-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5059f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5059f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5059f-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="5059f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5059f-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="5059f-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="5059f-108">[in] Eine TypeDef-Token, das den Typ mit Eigenschaften auflisten darstellt.</span><span class="sxs-lookup"><span data-stu-id="5059f-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="5059f-109">[out] Das Array zum Speichern der PropertyDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5059f-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5059f-110">[in] Die maximale Größe des `rProperties`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="5059f-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="5059f-111">[out] Die Anzahl der zurückgegebenen PropertyDef-Token `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="5059f-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5059f-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5059f-112">Return Value</span></span>  
  
|<span data-ttu-id="5059f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5059f-113">HRESULT</span></span>|<span data-ttu-id="5059f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5059f-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5059f-115">`EnumProperties` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5059f-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5059f-116">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="5059f-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="5059f-117">In diesem Fall `pcProperties` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="5059f-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5059f-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5059f-118">Requirements</span></span>  
 <span data-ttu-id="5059f-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5059f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5059f-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5059f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5059f-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5059f-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5059f-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5059f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5059f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5059f-123">See also</span></span>

- [<span data-ttu-id="5059f-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5059f-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5059f-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5059f-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
