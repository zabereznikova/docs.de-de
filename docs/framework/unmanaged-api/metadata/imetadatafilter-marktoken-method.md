---
title: IMetaDataFilter::MarkToken-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::MarkToken
helpviewer_keywords:
- IMetaDataFilter::MarkToken method [.NET Framework metadata]
- MarkToken method, IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: bd492834-6529-4d39-b93d-f8cdbd3e297f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08340c82acb8eff2ce5b778c719f350b58b51fa5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757534"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="f3b81-102">IMetaDataFilter::MarkToken-Methode</span><span class="sxs-lookup"><span data-stu-id="f3b81-102">IMetaDataFilter::MarkToken Method</span></span>
<span data-ttu-id="f3b81-103">Legt einen Wert, der angibt, dass das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="f3b81-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3b81-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3b81-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3b81-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f3b81-106">[in] Das Token als verarbeitet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f3b81-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3b81-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3b81-107">Requirements</span></span>  
 <span data-ttu-id="f3b81-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3b81-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3b81-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f3b81-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3b81-110">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f3b81-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f3b81-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3b81-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b81-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3b81-112">See also</span></span>

- [<span data-ttu-id="f3b81-113">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3b81-113">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
