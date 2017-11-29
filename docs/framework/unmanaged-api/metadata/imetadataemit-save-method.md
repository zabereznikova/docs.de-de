---
title: IMetaDataEmit::Save-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.Save
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8a2e77ad9ce66a04ef0530dc41f9795c501eed9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="f80c5-102">IMetaDataEmit::Save-Methode</span><span class="sxs-lookup"><span data-stu-id="f80c5-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="f80c5-103">Speichert alle Metadaten im aktuellen Bereich für die Datei an der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="f80c5-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f80c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f80c5-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f80c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f80c5-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="f80c5-106">[in] Der Name der Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f80c5-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="f80c5-107">Wenn dieser Wert null ist, wird die Kopie im Arbeitsspeicher bis zum letzten Speicherort gespeichert, der verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f80c5-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="f80c5-108">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="f80c5-108">[in] Reserved.</span></span> <span data-ttu-id="f80c5-109">NULL muss sein.</span><span class="sxs-lookup"><span data-stu-id="f80c5-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f80c5-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f80c5-110">Requirements</span></span>  
 <span data-ttu-id="f80c5-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f80c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f80c5-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f80c5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f80c5-113">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f80c5-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f80c5-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f80c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f80c5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f80c5-115">See Also</span></span>  
 [<span data-ttu-id="f80c5-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f80c5-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="f80c5-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f80c5-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
