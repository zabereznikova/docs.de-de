---
title: IMetaDataEmit::GetTokenFromSig-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 940d913b2b04a510e2ae0e33eaa78b07ba4237c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676795"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="13ae6-102">IMetaDataEmit::GetTokenFromSig-Methode</span><span class="sxs-lookup"><span data-stu-id="13ae6-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="13ae6-103">Ruft ein Token für die angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="13ae6-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13ae6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13ae6-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13ae6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13ae6-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="13ae6-106">[in] Die Signatur, die beibehalten und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="13ae6-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="13ae6-107">[in] Die Anzahl der Bytes im `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="13ae6-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="13ae6-108">[out] Die `mdSignature` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="13ae6-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13ae6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13ae6-109">Requirements</span></span>  
 <span data-ttu-id="13ae6-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13ae6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13ae6-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13ae6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13ae6-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="13ae6-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13ae6-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13ae6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ae6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13ae6-114">See also</span></span>
- [<span data-ttu-id="13ae6-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13ae6-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="13ae6-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13ae6-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
