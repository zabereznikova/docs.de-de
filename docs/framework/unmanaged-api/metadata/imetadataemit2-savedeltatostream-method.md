---
title: IMetaDataEmit2::SaveDeltaToStream-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bcfd90da200e04e5834b21ea84a3a84acc5b732d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="67bfe-102">IMetaDataEmit2::SaveDeltaToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="67bfe-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="67bfe-103">Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und Fortfahren im angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="67bfe-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67bfe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67bfe-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67bfe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67bfe-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="67bfe-106">[in] Ein Schnittstellenzeiger auf den schreibbaren Datenstrom an, um Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="67bfe-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="67bfe-107">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="67bfe-107">[in] Reserved.</span></span> <span data-ttu-id="67bfe-108">Dieser Wert muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="67bfe-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67bfe-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67bfe-109">Requirements</span></span>  
 <span data-ttu-id="67bfe-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67bfe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67bfe-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="67bfe-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67bfe-112">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="67bfe-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67bfe-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67bfe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67bfe-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67bfe-114">See Also</span></span>  
 [<span data-ttu-id="67bfe-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67bfe-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="67bfe-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67bfe-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
