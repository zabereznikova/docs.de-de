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
ms.openlocfilehash: ab5200cbd3a37bba31d52f9934e11aecc88c59c0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502409"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="293eb-102">IMetaDataImport::EnumParams-Methode</span><span class="sxs-lookup"><span data-stu-id="293eb-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="293eb-103">Zählt ParamDef-Token auf, die die Parameter der Methode darstellen, auf die vom angegebenen MethodDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="293eb-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="293eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="293eb-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="293eb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="293eb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="293eb-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="293eb-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="293eb-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="293eb-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="293eb-108">[in] Ein MethodDef-Token, das die Methode mit den Parametern auflisten darstellt.</span><span class="sxs-lookup"><span data-stu-id="293eb-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="293eb-109">[out] Das Array zum Speichern der ParamDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="293eb-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="293eb-110">[in] Die maximale Größe des `rParams`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="293eb-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="293eb-111">[out] Die Anzahl der zurückgegebenen ParamDef-Token `rParams`.</span><span class="sxs-lookup"><span data-stu-id="293eb-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="293eb-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="293eb-112">Return Value</span></span>  
  
|<span data-ttu-id="293eb-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="293eb-113">HRESULT</span></span>|<span data-ttu-id="293eb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="293eb-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="293eb-115">`EnumParams` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="293eb-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="293eb-116">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="293eb-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="293eb-117">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="293eb-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="293eb-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="293eb-118">Requirements</span></span>  
 <span data-ttu-id="293eb-119">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="293eb-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="293eb-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="293eb-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="293eb-121">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="293eb-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="293eb-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="293eb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="293eb-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="293eb-123">See also</span></span>
- [<span data-ttu-id="293eb-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="293eb-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="293eb-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="293eb-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
