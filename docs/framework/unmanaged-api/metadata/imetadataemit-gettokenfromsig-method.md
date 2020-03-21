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
ms.openlocfilehash: d02943f28435fc00aad8e319aa260a24cca5e307
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177591"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="d9f27-102">IMetaDataEmit::GetTokenFromSig-Methode</span><span class="sxs-lookup"><span data-stu-id="d9f27-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="d9f27-103">Ruft ein Token für die angegebene Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="d9f27-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9f27-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9f27-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9f27-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9f27-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="d9f27-106">[in] Die Signatur, die beibehalten und gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d9f27-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="d9f27-107">[in] Die Anzahl der `pvSig`Bytes in .</span><span class="sxs-lookup"><span data-stu-id="d9f27-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="d9f27-108">[out] Das `mdSignature` token zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d9f27-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9f27-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d9f27-109">Requirements</span></span>  
 <span data-ttu-id="d9f27-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9f27-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9f27-111">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9f27-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9f27-112">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d9f27-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9f27-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9f27-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f27-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9f27-114">See also</span></span>

- [<span data-ttu-id="d9f27-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9f27-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d9f27-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9f27-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
