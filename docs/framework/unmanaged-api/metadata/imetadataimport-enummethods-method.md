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
ms.openlocfilehash: 933694a6a033dbfe817e3848b9008f05b86f51f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449011"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="35967-102">IMetaDataImport::EnumMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="35967-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="35967-103">Zählt MethodDef-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="35967-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35967-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35967-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35967-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="35967-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="35967-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="35967-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="35967-107">Dies muss für den ersten Aufruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="35967-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="35967-108">[in] Eine TypeDef-Token, das den Typ mit den Methoden zum Aufzählen darstellt.</span><span class="sxs-lookup"><span data-stu-id="35967-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="35967-109">[out] Das Array zum Speichern der MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="35967-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="35967-110">[in] Die maximale Größe des MethodDef- `rMethods` Array.</span><span class="sxs-lookup"><span data-stu-id="35967-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="35967-111">[out] Die Anzahl der zurückgegebenen MethodDef-Token `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="35967-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35967-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35967-112">Return Value</span></span>  
  
|<span data-ttu-id="35967-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35967-113">HRESULT</span></span>|<span data-ttu-id="35967-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35967-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="35967-115">`EnumMethods` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="35967-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="35967-116">Es sind keine MethodDef-Token, aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="35967-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="35967-117">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="35967-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35967-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35967-118">Requirements</span></span>  
 <span data-ttu-id="35967-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35967-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35967-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35967-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35967-121">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="35967-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35967-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35967-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35967-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35967-123">See Also</span></span>  
 [<span data-ttu-id="35967-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35967-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="35967-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35967-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
