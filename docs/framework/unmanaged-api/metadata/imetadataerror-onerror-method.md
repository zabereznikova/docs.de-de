---
title: IMetaDataError::OnError-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataError.OnError
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7b8947f0bac8b51e704fbbb9085cf48740b3197d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="c5453-102">IMetaDataError::OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="c5453-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="c5453-103">Stellt eine Benachrichtigung von Fehlern, die auftreten, während das Zusammenführen von Metadaten bereit.</span><span class="sxs-lookup"><span data-stu-id="c5453-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5453-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5453-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5453-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5453-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="c5453-106">[in] Der HRESULT-Fehlerwert zurückgegeben, an die aufrufende Methode.</span><span class="sxs-lookup"><span data-stu-id="c5453-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="c5453-107">[in] Das Metadatentoken des Codeobjekts, die zusammengeführt wurde, als der Fehler auftrat.</span><span class="sxs-lookup"><span data-stu-id="c5453-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5453-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5453-108">Requirements</span></span>  
 <span data-ttu-id="c5453-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5453-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5453-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c5453-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5453-111">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c5453-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5453-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5453-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5453-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5453-113">See Also</span></span>  
 [<span data-ttu-id="c5453-114">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5453-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
