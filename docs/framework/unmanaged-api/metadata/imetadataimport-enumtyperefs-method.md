---
title: IMetaDataImport::EnumTypeRefs-Methode
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
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3099f129abd3477aeb08526b9f0dcd5b701d4dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="31c37-102">IMetaDataImport::EnumTypeRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="31c37-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="31c37-103">Zählt TypeRef-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="31c37-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31c37-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31c37-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31c37-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31c37-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="31c37-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="31c37-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="31c37-107">Dies muss für den ersten Aufruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="31c37-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="31c37-108">[out] Das Array zum Speichern der TypeRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31c37-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="31c37-109">[in] Die maximale Größe des `rTypeRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="31c37-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="31c37-110">[out] Ein Zeiger auf die Anzahl der zurückgegebenen TypeRef-Token `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="31c37-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31c37-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="31c37-111">Return Value</span></span>  
  
|<span data-ttu-id="31c37-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31c37-112">HRESULT</span></span>|<span data-ttu-id="31c37-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31c37-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="31c37-114">`EnumTypeRefs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="31c37-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="31c37-115">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="31c37-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="31c37-116">In diesem Fall `pcTypeRefs` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="31c37-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31c37-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31c37-117">Remarks</span></span>  
 <span data-ttu-id="31c37-118">Ein TypeRef-Token stellt einen Verweis auf einen Typ.</span><span class="sxs-lookup"><span data-stu-id="31c37-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31c37-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31c37-119">Requirements</span></span>  
 <span data-ttu-id="31c37-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31c37-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31c37-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="31c37-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31c37-122">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="31c37-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31c37-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31c37-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c37-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31c37-124">See Also</span></span>  
 [<span data-ttu-id="31c37-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31c37-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="31c37-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31c37-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
