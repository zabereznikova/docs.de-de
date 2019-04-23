---
title: IMetaDataTables::GetGuidHeapSize-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 812794bc76d475c516effdc950ca6a0b877494c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178359"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="be8f0-102">IMetaDataTables::GetGuidHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="be8f0-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="be8f0-103">Ruft die Größe in Bytes der GUID-Heap an.</span><span class="sxs-lookup"><span data-stu-id="be8f0-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be8f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be8f0-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be8f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be8f0-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="be8f0-106">[out] Ein Zeiger auf die Größe in Bytes der GUID-Heap.</span><span class="sxs-lookup"><span data-stu-id="be8f0-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be8f0-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be8f0-107">Requirements</span></span>  
 <span data-ttu-id="be8f0-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be8f0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be8f0-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="be8f0-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be8f0-110">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="be8f0-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="be8f0-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be8f0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be8f0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be8f0-112">See also</span></span>

- [<span data-ttu-id="be8f0-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be8f0-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="be8f0-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be8f0-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
