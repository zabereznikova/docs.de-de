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
ms.openlocfilehash: c942838fb62bf86c4054761f4e7f2ef0518b3d89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701808"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="20023-102">IMetaDataFilter::MarkToken-Methode</span><span class="sxs-lookup"><span data-stu-id="20023-102">IMetaDataFilter::MarkToken Method</span></span>

<span data-ttu-id="20023-103">Legt einen Wert fest, der angibt, dass das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="20023-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20023-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20023-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20023-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20023-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="20023-106">in Das Token, das als verarbeitet markiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="20023-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20023-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="20023-107">Requirements</span></span>  

 <span data-ttu-id="20023-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20023-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20023-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="20023-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20023-110">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="20023-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="20023-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20023-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20023-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20023-112">See also</span></span>

- [<span data-ttu-id="20023-113">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20023-113">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
