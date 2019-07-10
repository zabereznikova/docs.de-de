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
ms.openlocfilehash: afc2192fe46ed75ed6fb75e0d58268152856b746
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770782"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="f04ad-102">IMetaDataEmit::GetTokenFromSig-Methode</span><span class="sxs-lookup"><span data-stu-id="f04ad-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="f04ad-103">Ruft ein Token für die angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="f04ad-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f04ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f04ad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f04ad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f04ad-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="f04ad-106">[in] Die Signatur, die beibehalten und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f04ad-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="f04ad-107">[in] Die Anzahl der Bytes im `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="f04ad-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="f04ad-108">[out] Die `mdSignature` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="f04ad-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f04ad-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f04ad-109">Requirements</span></span>  
 <span data-ttu-id="f04ad-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f04ad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f04ad-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f04ad-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f04ad-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f04ad-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f04ad-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f04ad-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04ad-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f04ad-114">See also</span></span>

- [<span data-ttu-id="f04ad-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f04ad-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f04ad-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f04ad-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
