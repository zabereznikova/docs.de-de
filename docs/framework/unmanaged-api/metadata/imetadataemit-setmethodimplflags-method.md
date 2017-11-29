---
title: IMetaDataEmit::SetMethodImplFlags-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetMethodImplFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d69940d5cffe397d009b7364a20a09dbbd95db4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="f8310-102">IMetaDataEmit::SetMethodImplFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="f8310-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="f8310-103">Legt fest oder aktualisiert die Metadatensignatur der geerbte Methode-Implementierung, die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f8310-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8310-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8310-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8310-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8310-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="f8310-106">[in] Das Token für die Methode geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f8310-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="f8310-107">[in] Eine Kombination der Werte für die [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) Enumeration, die Features zur Implementierung der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="f8310-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8310-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8310-108">Requirements</span></span>  
 <span data-ttu-id="f8310-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8310-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8310-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f8310-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8310-111">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f8310-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8310-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8310-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8310-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8310-113">See Also</span></span>  
 [<span data-ttu-id="f8310-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8310-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="f8310-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8310-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
