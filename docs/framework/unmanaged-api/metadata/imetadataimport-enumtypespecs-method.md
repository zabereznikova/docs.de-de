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
ms.openlocfilehash: a872af384a8df624178d8d37d5ad98a0b5c561d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="45b6b-102">IMetaDataImport::EnumTypeSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="45b6b-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="45b6b-103">Zählt TypeSpec-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="45b6b-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45b6b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45b6b-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45b6b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45b6b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="45b6b-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="45b6b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="45b6b-107">Dieser Wert muss NULL für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="45b6b-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="45b6b-108">[out] Das Array zum Speichern der TypeSpec-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="45b6b-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="45b6b-109">[in] Die maximale Größe des `rTypeSpecs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="45b6b-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="45b6b-110">[out] Die Anzahl der TypeSpec-Token im zurückgegebenen `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="45b6b-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45b6b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="45b6b-111">Return Value</span></span>  
  
|<span data-ttu-id="45b6b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45b6b-112">HRESULT</span></span>|<span data-ttu-id="45b6b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45b6b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="45b6b-114">`EnumTypeSpecs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="45b6b-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="45b6b-115">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="45b6b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="45b6b-116">In diesem Fall `pcTypeSpecs` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="45b6b-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45b6b-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45b6b-117">Remarks</span></span>  
 <span data-ttu-id="45b6b-118">Die TypeSpec-Token werden erstellt, indem die [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="45b6b-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45b6b-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45b6b-119">Requirements</span></span>  
 <span data-ttu-id="45b6b-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45b6b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45b6b-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="45b6b-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45b6b-122">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="45b6b-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45b6b-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45b6b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45b6b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45b6b-124">See Also</span></span>  
 [<span data-ttu-id="45b6b-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45b6b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="45b6b-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45b6b-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
