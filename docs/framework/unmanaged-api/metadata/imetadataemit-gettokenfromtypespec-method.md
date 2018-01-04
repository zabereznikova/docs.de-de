---
title: IMetaDataEmit::GetTokenFromTypeSpec-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetTokenFromTypeSpec
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6acb9d340aa1dc8df5d0b9dc3b0c0dd9c159257e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="49171-102">IMetaDataEmit::GetTokenFromTypeSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="49171-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="49171-103">Ruft ein Metadatentoken für den Typ mit der angegebenen Metadaten-Signatur.</span><span class="sxs-lookup"><span data-stu-id="49171-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49171-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49171-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49171-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49171-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="49171-106">[in] Die Signatur, die definiert wird.</span><span class="sxs-lookup"><span data-stu-id="49171-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="49171-107">[in] Die Anzahl der Bytes im `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="49171-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="49171-108">[out] Die `mdTypeSpec` Token zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="49171-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49171-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49171-109">Requirements</span></span>  
 <span data-ttu-id="49171-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49171-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49171-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="49171-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49171-112">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="49171-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49171-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49171-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49171-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49171-114">See Also</span></span>  
 [<span data-ttu-id="49171-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49171-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="49171-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49171-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
