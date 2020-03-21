---
title: IMetaDataFilter::IsTokenMarked-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
ms.openlocfilehash: 47377e892aaf2bdd96a297630c47fe52215b0564
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177382"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="df7a8-102">IMetaDataFilter::IsTokenMarked-Methode</span><span class="sxs-lookup"><span data-stu-id="df7a8-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="df7a8-103">Ruft einen Wert ab, der angibt, ob das angegebene Metadatentoken als verarbeitet markiert wurde.</span><span class="sxs-lookup"><span data-stu-id="df7a8-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df7a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df7a8-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df7a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df7a8-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="df7a8-106">[in] Das Token, das auf eine Verarbeitungsmarke untersucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="df7a8-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="df7a8-107">[out] Ein Wert, `true` `tk` der verarbeitet wurde; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="df7a8-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df7a8-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="df7a8-108">Requirements</span></span>  
 <span data-ttu-id="df7a8-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df7a8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df7a8-110">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="df7a8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df7a8-111">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="df7a8-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df7a8-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df7a8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7a8-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df7a8-113">See also</span></span>

- [<span data-ttu-id="df7a8-114">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df7a8-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
