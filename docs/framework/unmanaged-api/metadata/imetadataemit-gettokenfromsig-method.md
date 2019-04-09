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
ms.openlocfilehash: 242618fb2a5ab748132baf68e24240d1ffaf2301
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139840"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="2eb63-102">IMetaDataEmit::GetTokenFromSig-Methode</span><span class="sxs-lookup"><span data-stu-id="2eb63-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="2eb63-103">Ruft ein Token für die angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="2eb63-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eb63-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2eb63-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2eb63-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2eb63-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="2eb63-106">[in] Die Signatur, die beibehalten und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2eb63-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="2eb63-107">[in] Die Anzahl der Bytes im `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="2eb63-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="2eb63-108">[out] Die `mdSignature` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="2eb63-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2eb63-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2eb63-109">Requirements</span></span>  
 <span data-ttu-id="2eb63-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2eb63-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eb63-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2eb63-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2eb63-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2eb63-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2eb63-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2eb63-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2eb63-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2eb63-114">See also</span></span>

- [<span data-ttu-id="2eb63-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2eb63-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2eb63-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2eb63-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
