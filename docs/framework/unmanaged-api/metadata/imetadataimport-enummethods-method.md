---
title: IMetaDataImport::EnumMethods-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 668c7298a9543cce93cce324672334c9ec1e8cd2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732816"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="0294b-102">IMetaDataImport::EnumMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="0294b-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="0294b-103">Zählt MethodDef-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="0294b-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0294b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0294b-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0294b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0294b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0294b-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="0294b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0294b-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="0294b-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="0294b-108">[in] Eine TypeDef-Token, das mit den Methoden zum Aufzählen der Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="0294b-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="0294b-109">[out] Das Array zum Speichern der MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="0294b-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0294b-110">[in] Die maximale Größe der MethodDef `rMethods` Array.</span><span class="sxs-lookup"><span data-stu-id="0294b-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0294b-111">[out] Die Anzahl der zurückgegebenen MethodDef-Token `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="0294b-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0294b-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0294b-112">Return Value</span></span>  
  
|<span data-ttu-id="0294b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0294b-113">HRESULT</span></span>|<span data-ttu-id="0294b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0294b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0294b-115">`EnumMethods` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0294b-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0294b-116">Es sind keine MethodDef-Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="0294b-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="0294b-117">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="0294b-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0294b-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0294b-118">Requirements</span></span>  
 <span data-ttu-id="0294b-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0294b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0294b-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0294b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0294b-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0294b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0294b-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0294b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0294b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0294b-123">See also</span></span>
- [<span data-ttu-id="0294b-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0294b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0294b-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0294b-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
