---
title: IMetaDataTables::GetUserStringHeapSize-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1215da0816c1fc7cdfaee0da167118909f8e5eb3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466101"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="331d6-102">IMetaDataTables::GetUserStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="331d6-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="331d6-103">Ruft die Größe in Bytes, der dem Benutzer String-Heap an.</span><span class="sxs-lookup"><span data-stu-id="331d6-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="331d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="331d6-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="331d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="331d6-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="331d6-106">[out] Ein Zeiger auf die Größe in Bytes, der dem Benutzer String-Heap.</span><span class="sxs-lookup"><span data-stu-id="331d6-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="331d6-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="331d6-107">Requirements</span></span>  
 <span data-ttu-id="331d6-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="331d6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="331d6-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="331d6-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="331d6-110">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="331d6-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="331d6-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="331d6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="331d6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="331d6-112">See also</span></span>
- [<span data-ttu-id="331d6-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="331d6-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="331d6-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="331d6-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
