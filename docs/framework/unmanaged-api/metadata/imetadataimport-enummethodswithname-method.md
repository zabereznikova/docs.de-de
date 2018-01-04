---
title: IMetaDataImport::EnumMethodsWithName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodsWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f16e66f83925104c4be1e69a476e398f33295a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="64baf-102">IMetaDataImport::EnumMethodsWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="64baf-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="64baf-103">Zählt Methoden auf, die den angegebenen Namen aufweisen und durch den Typ definiert sind, auf den durch das angegebene TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="64baf-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64baf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64baf-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64baf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="64baf-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="64baf-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="64baf-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="64baf-107">Dies muss für den ersten Aufruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="64baf-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="64baf-108">[in] Eine TypeDef-Token, das den Typ darstellt, dessen Methoden zum Aufzählen.</span><span class="sxs-lookup"><span data-stu-id="64baf-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="64baf-109">[in] Der Name, der den Bereich der Enumeration einschränkt.</span><span class="sxs-lookup"><span data-stu-id="64baf-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="64baf-110">[out] Das Array zum Speichern der MethodDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="64baf-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="64baf-111">[in] Die maximale Größe des `rMethods`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="64baf-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="64baf-112">[out] Die Anzahl der zurückgegebenen MethodDef-Token `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="64baf-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64baf-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64baf-113">Remarks</span></span>  
 <span data-ttu-id="64baf-114">Diese Methode listet Felder und Methoden, jedoch keine Eigenschaften oder Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="64baf-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="64baf-115">Im Gegensatz zu [IMetaDataImport:: EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` verwirft alle Methodentoken, die nicht mit den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="64baf-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64baf-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="64baf-116">Return Value</span></span>  
  
|<span data-ttu-id="64baf-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64baf-117">HRESULT</span></span>|<span data-ttu-id="64baf-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64baf-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="64baf-119">`EnumMethodsWithName`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="64baf-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="64baf-120">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="64baf-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="64baf-121">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="64baf-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64baf-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64baf-122">Requirements</span></span>  
 <span data-ttu-id="64baf-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64baf-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64baf-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="64baf-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64baf-125">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="64baf-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="64baf-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64baf-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64baf-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64baf-127">See Also</span></span>  
 [<span data-ttu-id="64baf-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64baf-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="64baf-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64baf-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
