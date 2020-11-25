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
ms.openlocfilehash: b41891227d94b66bf59128d620eba9da117fe92a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722049"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="43b95-102">IMetaDataEmit::GetTokenFromSig-Methode</span><span class="sxs-lookup"><span data-stu-id="43b95-102">IMetaDataEmit::GetTokenFromSig Method</span></span>

<span data-ttu-id="43b95-103">Ruft ein Token für die angegebene Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="43b95-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43b95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43b95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43b95-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="43b95-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="43b95-106">in Die Signatur, die persistent gespeichert und gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="43b95-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="43b95-107">in Die Anzahl von Bytes in `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="43b95-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="43b95-108">vorgenommen Das `mdSignature` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="43b95-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43b95-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="43b95-109">Requirements</span></span>  

 <span data-ttu-id="43b95-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43b95-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43b95-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="43b95-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43b95-112">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="43b95-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43b95-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43b95-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b95-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43b95-114">See also</span></span>

- [<span data-ttu-id="43b95-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43b95-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="43b95-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43b95-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
