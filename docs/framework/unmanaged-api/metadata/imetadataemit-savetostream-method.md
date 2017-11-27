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
ms.openlocfilehash: 97f65fb6cfb7067ed4e6929772f0f114cedcf787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="195b8-102">IMetaDataEmit::SaveToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="195b8-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="195b8-103">Speichert alle Metadaten im aktuellen Bereich für den angegebenen `IStream`.</span><span class="sxs-lookup"><span data-stu-id="195b8-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="195b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="195b8-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="195b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="195b8-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="195b8-106">[in] Der schreibbaren Datenstrom zu speichern.</span><span class="sxs-lookup"><span data-stu-id="195b8-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="195b8-107">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="195b8-107">[in] Reserved.</span></span> <span data-ttu-id="195b8-108">NULL muss sein.</span><span class="sxs-lookup"><span data-stu-id="195b8-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="195b8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="195b8-109">Requirements</span></span>  
 <span data-ttu-id="195b8-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="195b8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="195b8-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="195b8-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="195b8-112">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="195b8-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="195b8-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="195b8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195b8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="195b8-114">See Also</span></span>  
 [<span data-ttu-id="195b8-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="195b8-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="195b8-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="195b8-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
