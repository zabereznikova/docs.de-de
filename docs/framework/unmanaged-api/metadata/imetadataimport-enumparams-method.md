---
title: IMetaDataImport::EnumParams-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b848c30e824d45f6f619cfdb3d00a2d3cdc4573e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448712"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="b3040-102">IMetaDataImport::EnumParams-Methode</span><span class="sxs-lookup"><span data-stu-id="b3040-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="b3040-103">Zählt ParamDef-Token auf, die die Parameter der Methode darstellen, auf die vom angegebenen MethodDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b3040-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3040-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3040-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3040-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b3040-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b3040-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="b3040-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b3040-107">Dies muss für den ersten Aufruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="b3040-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="b3040-108">[in] Ein MethodDef-Token, das die Methode mit den Parametern zum Aufzählen darstellt.</span><span class="sxs-lookup"><span data-stu-id="b3040-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="b3040-109">[out] Das Array zum Speichern der ParamDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3040-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b3040-110">[in] Die maximale Größe des `rParams`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b3040-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b3040-111">[out] Die Anzahl der zurückgegebenen ParamDef-Token `rParams`.</span><span class="sxs-lookup"><span data-stu-id="b3040-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3040-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b3040-112">Return Value</span></span>  
  
|<span data-ttu-id="b3040-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3040-113">HRESULT</span></span>|<span data-ttu-id="b3040-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3040-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b3040-115">`EnumParams` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b3040-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b3040-116">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="b3040-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="b3040-117">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="b3040-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3040-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3040-118">Requirements</span></span>  
 <span data-ttu-id="b3040-119">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3040-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3040-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b3040-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3040-121">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="b3040-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3040-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3040-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3040-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3040-123">See Also</span></span>  
 [<span data-ttu-id="b3040-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3040-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b3040-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3040-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
