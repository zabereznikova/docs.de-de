---
title: IMetaDataEmit::GetTokenFromTypeSpec-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b0b7d0364b6f58579ee8573d168d6c8180ac9dff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444576"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="9aaa2-102">IMetaDataEmit::GetTokenFromTypeSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="9aaa2-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="9aaa2-103">Ruft ein Metadatentoken für den Typ mit der angegebenen Metadaten-Signatur.</span><span class="sxs-lookup"><span data-stu-id="9aaa2-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aaa2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9aaa2-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9aaa2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9aaa2-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="9aaa2-106">[in] Die Signatur, die definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9aaa2-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="9aaa2-107">[in] Die Anzahl der Bytes im `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="9aaa2-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="9aaa2-108">[out] Die `mdTypeSpec` Token zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9aaa2-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aaa2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9aaa2-109">Requirements</span></span>  
 <span data-ttu-id="9aaa2-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9aaa2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aaa2-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9aaa2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9aaa2-112">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9aaa2-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9aaa2-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aaa2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aaa2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9aaa2-114">See Also</span></span>  
 [<span data-ttu-id="9aaa2-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9aaa2-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9aaa2-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9aaa2-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
