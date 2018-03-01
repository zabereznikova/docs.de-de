---
title: IMetaDataTables::GetUserStringHeapSize-Methode
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
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4b1f4f1b8c3cafb28c2b84867dbe5ac3f8424e8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="f3f3e-102">IMetaDataTables::GetUserStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="f3f3e-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="f3f3e-103">Ruft die Größe des dem Benutzer String-Heap in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="f3f3e-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3f3e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3f3e-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3f3e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3f3e-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="f3f3e-106">[out] Ein Zeiger auf die Größe in Bytes, der dem Benutzer String-Heap.</span><span class="sxs-lookup"><span data-stu-id="f3f3e-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3f3e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3f3e-107">Requirements</span></span>  
 <span data-ttu-id="f3f3e-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3f3e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3f3e-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f3f3e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3f3e-110">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f3f3e-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f3f3e-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3f3e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f3e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3f3e-112">See Also</span></span>  
 [<span data-ttu-id="f3f3e-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3f3e-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="f3f3e-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3f3e-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
