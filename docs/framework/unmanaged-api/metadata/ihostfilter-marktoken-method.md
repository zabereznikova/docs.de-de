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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96f0b1648c8182b4d075a479f9bd376dbe33ef61
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487902"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="903c5-102">IHostFilter::MarkToken-Methode</span><span class="sxs-lookup"><span data-stu-id="903c5-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="903c5-103">Gibt an, dass das angegebene Metadatentoken verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="903c5-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="903c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="903c5-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="903c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="903c5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="903c5-106">[in] Das Metadatentoken verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="903c5-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="903c5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="903c5-107">Remarks</span></span>  
 <span data-ttu-id="903c5-108">In der Regel sollten Sie ein Token verarbeitet werden, wenn sie im Metadatenbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="903c5-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="903c5-109">Die `MarkToken` Methode übergeben wird, um die Metadaten-Engine über die [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="903c5-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="903c5-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="903c5-110">Requirements</span></span>  
 <span data-ttu-id="903c5-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="903c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="903c5-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="903c5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="903c5-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="903c5-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="903c5-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="903c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903c5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="903c5-115">See also</span></span>
- [<span data-ttu-id="903c5-116">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="903c5-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="903c5-117">IHostFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="903c5-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
