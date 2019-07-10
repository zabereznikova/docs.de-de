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
ms.openlocfilehash: e15f4e8691db13b9a646a1e1d783075acfcdd896
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777078"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="af9a3-102">IMetaDataFilter::IsTokenMarked-Methode</span><span class="sxs-lookup"><span data-stu-id="af9a3-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="af9a3-103">Ruft einen Wert, der angibt, ob das angegebene Metadatentoken als verarbeitet gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="af9a3-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af9a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af9a3-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af9a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af9a3-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="af9a3-106">[in] Das Token, um eine Markierung für die Verarbeitung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="af9a3-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="af9a3-107">[out] Ein Wert, `true` Wenn `tk` wurde verarbeitet wird; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="af9a3-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af9a3-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af9a3-108">Requirements</span></span>  
 <span data-ttu-id="af9a3-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af9a3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af9a3-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="af9a3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af9a3-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="af9a3-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af9a3-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af9a3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af9a3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af9a3-113">See also</span></span>

- [<span data-ttu-id="af9a3-114">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af9a3-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
