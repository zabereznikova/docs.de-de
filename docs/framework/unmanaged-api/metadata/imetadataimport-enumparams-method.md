---
title: IMetaDataImport::EnumParams-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumParams
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 42555e1300016222e9ea8064e90fa3062d79db6a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="337c7-102">IMetaDataImport::EnumParams-Methode</span><span class="sxs-lookup"><span data-stu-id="337c7-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="337c7-103">Zählt ParamDef-Token auf, die die Parameter der Methode darstellen, auf die vom angegebenen MethodDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="337c7-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="337c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="337c7-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="337c7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="337c7-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="337c7-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="337c7-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="337c7-107">Dies muss für den ersten Aufruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="337c7-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="337c7-108">[in] Ein MethodDef-Token, das die Methode mit den Parametern zum Aufzählen darstellt.</span><span class="sxs-lookup"><span data-stu-id="337c7-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="337c7-109">[out] Das Array zum Speichern der ParamDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="337c7-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="337c7-110">[in] Die maximale Größe des `rParams`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="337c7-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="337c7-111">[out] Die Anzahl der zurückgegebenen ParamDef-Token `rParams`.</span><span class="sxs-lookup"><span data-stu-id="337c7-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="337c7-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="337c7-112">Return Value</span></span>  
  
|<span data-ttu-id="337c7-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="337c7-113">HRESULT</span></span>|<span data-ttu-id="337c7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="337c7-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="337c7-115">`EnumParams`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="337c7-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="337c7-116">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="337c7-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="337c7-117">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="337c7-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="337c7-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="337c7-118">Requirements</span></span>  
 <span data-ttu-id="337c7-119">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="337c7-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="337c7-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="337c7-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="337c7-121">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="337c7-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="337c7-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337c7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337c7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="337c7-123">See Also</span></span>  
 [<span data-ttu-id="337c7-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="337c7-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="337c7-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="337c7-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
