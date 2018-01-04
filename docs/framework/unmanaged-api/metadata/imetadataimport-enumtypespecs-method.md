---
title: IMetaDataImport::EnumTypeSpecs-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumTypeSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e34a3086474918c913a366c02bbf9eadf313b43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="fb193-102">IMetaDataImport::EnumTypeSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="fb193-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="fb193-103">Zählt TypeSpec-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="fb193-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb193-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb193-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb193-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fb193-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fb193-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="fb193-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fb193-107">Dieser Wert muss NULL für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="fb193-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="fb193-108">[out] Das Array zum Speichern der TypeSpec-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb193-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fb193-109">[in] Die maximale Größe des `rTypeSpecs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="fb193-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="fb193-110">[out] Die Anzahl der TypeSpec-Token im zurückgegebenen `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="fb193-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb193-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fb193-111">Return Value</span></span>  
  
|<span data-ttu-id="fb193-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb193-112">HRESULT</span></span>|<span data-ttu-id="fb193-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb193-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fb193-114">`EnumTypeSpecs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fb193-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fb193-115">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="fb193-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="fb193-116">In diesem Fall `pcTypeSpecs` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="fb193-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb193-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb193-117">Remarks</span></span>  
 <span data-ttu-id="fb193-118">Die TypeSpec-Token werden erstellt, indem die [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="fb193-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb193-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb193-119">Requirements</span></span>  
 <span data-ttu-id="fb193-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb193-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb193-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb193-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb193-122">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fb193-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb193-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb193-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb193-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb193-124">See Also</span></span>  
 [<span data-ttu-id="fb193-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb193-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="fb193-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb193-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
