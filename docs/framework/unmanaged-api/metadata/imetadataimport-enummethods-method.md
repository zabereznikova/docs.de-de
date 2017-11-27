---
title: IMetaDataImport::EnumMethods-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethods
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d56c87d7073886d13e530501168801c6c69d9ce9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="05bdb-102">IMetaDataImport::EnumMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="05bdb-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="05bdb-103">Zählt MethodDef-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="05bdb-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05bdb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05bdb-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05bdb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05bdb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="05bdb-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="05bdb-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="05bdb-107">Dies muss für den ersten Aufruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="05bdb-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="05bdb-108">[in] Eine TypeDef-Token, das den Typ mit den Methoden zum Aufzählen darstellt.</span><span class="sxs-lookup"><span data-stu-id="05bdb-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="05bdb-109">[out] Das Array zum Speichern der MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="05bdb-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="05bdb-110">[in] Die maximale Größe des MethodDef- `rMethods` Array.</span><span class="sxs-lookup"><span data-stu-id="05bdb-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="05bdb-111">[out] Die Anzahl der zurückgegebenen MethodDef-Token `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="05bdb-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05bdb-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05bdb-112">Return Value</span></span>  
  
|<span data-ttu-id="05bdb-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05bdb-113">HRESULT</span></span>|<span data-ttu-id="05bdb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05bdb-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="05bdb-115">`EnumMethods`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="05bdb-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="05bdb-116">Es sind keine MethodDef-Token, aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="05bdb-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="05bdb-117">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="05bdb-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05bdb-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="05bdb-118">Requirements</span></span>  
 <span data-ttu-id="05bdb-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05bdb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05bdb-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="05bdb-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05bdb-121">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="05bdb-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05bdb-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05bdb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05bdb-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05bdb-123">See Also</span></span>  
 [<span data-ttu-id="05bdb-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05bdb-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="05bdb-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05bdb-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
