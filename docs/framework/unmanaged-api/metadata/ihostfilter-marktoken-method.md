---
title: IHostFilter::MarkToken-Methode
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: b4db3b115517f0a146aeab469f091008d31efc86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718227"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="04ac6-102">IHostFilter::MarkToken-Methode</span><span class="sxs-lookup"><span data-stu-id="04ac6-102">IHostFilter::MarkToken Method</span></span>

<span data-ttu-id="04ac6-103">Gibt an, dass das angegebene Metadatentoken verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="04ac6-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04ac6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="04ac6-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04ac6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="04ac6-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="04ac6-106">in Das zu verarbeitende Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="04ac6-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04ac6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04ac6-107">Remarks</span></span>  

 <span data-ttu-id="04ac6-108">In der Regel möchten Sie, dass ein Token verarbeitet wird, wenn es sich im Metadatenbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="04ac6-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="04ac6-109">Die- `MarkToken` Methode wird über die [IMetaDataEmit:: lthandler](imetadataemit-sethandler-method.md) -Methode an die metadatenengine übermittelt.</span><span class="sxs-lookup"><span data-stu-id="04ac6-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04ac6-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="04ac6-110">Requirements</span></span>  

 <span data-ttu-id="04ac6-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04ac6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04ac6-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="04ac6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04ac6-113">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="04ac6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04ac6-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04ac6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ac6-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04ac6-115">See also</span></span>

- [<span data-ttu-id="04ac6-116">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="04ac6-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="04ac6-117">IHostFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04ac6-117">IHostFilter Interface</span></span>](ihostfilter-interface.md)
