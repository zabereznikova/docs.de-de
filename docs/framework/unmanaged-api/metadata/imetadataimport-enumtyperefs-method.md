---
title: IMetaDataImport::EnumTypeRefs-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumTypeRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 890f70900f2a1d4909d1511791d4d22bb81d3a1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="a9e93-102">IMetaDataImport::EnumTypeRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="a9e93-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="a9e93-103">Zählt TypeRef-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a9e93-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9e93-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9e93-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9e93-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9e93-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a9e93-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="a9e93-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a9e93-107">Dies muss für den ersten Aufruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="a9e93-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="a9e93-108">[out] Das Array zum Speichern der TypeRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9e93-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a9e93-109">[in] Die maximale Größe des `rTypeRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a9e93-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="a9e93-110">[out] Ein Zeiger auf die Anzahl der zurückgegebenen TypeRef-Token `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="a9e93-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9e93-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a9e93-111">Return Value</span></span>  
  
|<span data-ttu-id="a9e93-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9e93-112">HRESULT</span></span>|<span data-ttu-id="a9e93-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9e93-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a9e93-114">`EnumTypeRefs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a9e93-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a9e93-115">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="a9e93-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a9e93-116">In diesem Fall `pcTypeRefs` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="a9e93-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9e93-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9e93-117">Remarks</span></span>  
 <span data-ttu-id="a9e93-118">Ein TypeRef-Token stellt einen Verweis auf einen Typ.</span><span class="sxs-lookup"><span data-stu-id="a9e93-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9e93-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a9e93-119">Requirements</span></span>  
 <span data-ttu-id="a9e93-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9e93-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9e93-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9e93-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9e93-122">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a9e93-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9e93-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9e93-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e93-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9e93-124">See Also</span></span>  
 [<span data-ttu-id="a9e93-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9e93-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a9e93-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9e93-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
