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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5bf5149e8e42a810a6a490767638b374f66b5679
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445863"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="d367a-102">IMetaDataFilter::IsTokenMarked-Methode</span><span class="sxs-lookup"><span data-stu-id="d367a-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="d367a-103">Ruft einen Wert, der angibt, ob das angegebene Metadatentoken als verarbeitet markiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d367a-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d367a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d367a-104">Syntax</span></span>  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d367a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d367a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="d367a-106">[in] Das Token für eine Markierung für die Verarbeitung zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="d367a-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="d367a-107">[out] Ein Wert, `true` Wenn `tk` wurde verarbeitet, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d367a-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d367a-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d367a-108">Requirements</span></span>  
 <span data-ttu-id="d367a-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d367a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d367a-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d367a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d367a-111">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d367a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d367a-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d367a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d367a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d367a-113">See Also</span></span>  
 [<span data-ttu-id="d367a-114">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d367a-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
