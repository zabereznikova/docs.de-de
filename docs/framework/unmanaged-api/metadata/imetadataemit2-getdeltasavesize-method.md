---
title: IMetaDataEmit2::GetDeltaSaveSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.GetDeltaSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0a1b3aec06d6593257c82d6e3c08d6a8e2430691
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="b703a-102">IMetaDataEmit2::GetDeltaSaveSize-Methode</span><span class="sxs-lookup"><span data-stu-id="b703a-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="b703a-103">Ruft einen Wert, der angibt, der keine Änderung an der Größe der Metadaten, die durch die aktuelle Sitzung mit bearbeiten und Fortfahren entsteht.</span><span class="sxs-lookup"><span data-stu-id="b703a-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b703a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b703a-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b703a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b703a-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="b703a-106">[in] Eines der [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) Werte, der den gewünschten Genauigkeitsgrad.</span><span class="sxs-lookup"><span data-stu-id="b703a-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="b703a-107">Für .NET Framework, Version 2.0 wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b703a-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="b703a-108">[out] Das Ändern der Größe der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="b703a-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b703a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b703a-109">Requirements</span></span>  
 <span data-ttu-id="b703a-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b703a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b703a-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b703a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b703a-112">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="b703a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b703a-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b703a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b703a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b703a-114">See Also</span></span>  
 [<span data-ttu-id="b703a-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b703a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="b703a-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b703a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
