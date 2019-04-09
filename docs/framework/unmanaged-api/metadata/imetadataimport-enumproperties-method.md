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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176032"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="cfb88-102">IMetaDataImport::EnumProperties-Methode</span><span class="sxs-lookup"><span data-stu-id="cfb88-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="cfb88-103">Zählt PropertyDef-Token auf, die die Eigenschaften des Typs darstellen, auf den vom angegebenen TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cfb88-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb88-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfb88-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfb88-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cfb88-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cfb88-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="cfb88-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="cfb88-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="cfb88-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="cfb88-108">[in] Eine TypeDef-Token, das den Typ mit Eigenschaften auflisten darstellt.</span><span class="sxs-lookup"><span data-stu-id="cfb88-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="cfb88-109">[out] Das Array zum Speichern der PropertyDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cfb88-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cfb88-110">[in] Die maximale Größe des `rProperties`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="cfb88-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="cfb88-111">[out] Die Anzahl der zurückgegebenen PropertyDef-Token `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="cfb88-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfb88-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cfb88-112">Return Value</span></span>  
  
|<span data-ttu-id="cfb88-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cfb88-113">HRESULT</span></span>|<span data-ttu-id="cfb88-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfb88-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumProperties` <span data-ttu-id="cfb88-115">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cfb88-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cfb88-116">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="cfb88-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="cfb88-117">In diesem Fall `pcProperties` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="cfb88-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cfb88-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cfb88-118">Requirements</span></span>  
 <span data-ttu-id="cfb88-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfb88-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfb88-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cfb88-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cfb88-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cfb88-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="cfb88-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cfb88-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cfb88-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfb88-123">See also</span></span>

- [<span data-ttu-id="cfb88-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfb88-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cfb88-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfb88-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
