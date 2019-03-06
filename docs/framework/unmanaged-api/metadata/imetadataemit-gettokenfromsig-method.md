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
ms.openlocfilehash: 2f94c12654626e149b0f75327e8fdfa55aefe697
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467116"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="12b72-102">IMetaDataEmit::GetTokenFromSig-Methode</span><span class="sxs-lookup"><span data-stu-id="12b72-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="12b72-103">Ruft ein Token für die angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="12b72-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b72-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12b72-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12b72-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="12b72-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="12b72-106">[in] Die Signatur, die beibehalten und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="12b72-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="12b72-107">[in] Die Anzahl der Bytes im `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="12b72-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="12b72-108">[out] Die `mdSignature` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="12b72-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12b72-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12b72-109">Requirements</span></span>  
 <span data-ttu-id="12b72-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12b72-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12b72-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="12b72-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12b72-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="12b72-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12b72-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12b72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b72-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12b72-114">See also</span></span>
- [<span data-ttu-id="12b72-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12b72-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="12b72-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12b72-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
