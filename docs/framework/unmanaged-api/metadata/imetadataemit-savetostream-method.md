---
title: IMetaDataEmit::SaveToStream-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SaveToStream
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 135faea41ab1a8165e315b8d0815abc48ba7fd38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="d8f28-102">IMetaDataEmit::SaveToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="d8f28-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="d8f28-103">Speichert alle Metadaten im aktuellen Bereich für den angegebenen `IStream`.</span><span class="sxs-lookup"><span data-stu-id="d8f28-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8f28-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8f28-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8f28-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8f28-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="d8f28-106">[in] Der schreibbaren Datenstrom zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d8f28-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="d8f28-107">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="d8f28-107">[in] Reserved.</span></span> <span data-ttu-id="d8f28-108">NULL muss sein.</span><span class="sxs-lookup"><span data-stu-id="d8f28-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8f28-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d8f28-109">Requirements</span></span>  
 <span data-ttu-id="d8f28-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8f28-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8f28-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d8f28-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d8f28-112">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d8f28-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8f28-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8f28-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f28-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8f28-114">See Also</span></span>  
 [<span data-ttu-id="d8f28-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8f28-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="d8f28-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8f28-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
