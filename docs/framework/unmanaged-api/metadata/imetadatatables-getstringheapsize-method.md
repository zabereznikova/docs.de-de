---
title: IMetaDataTables::GetStringHeapSize-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f6f16ebe57be0d09e97fe8aa95df892c2b02394
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696255"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="7fbfb-102">IMetaDataTables::GetStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="7fbfb-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="7fbfb-103">Ruft die Größe in Bytes, der dem String-Heap an.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fbfb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fbfb-104">Syntax</span></span>  
  
```  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7fbfb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7fbfb-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="7fbfb-106">[out] Ein Zeiger auf die Größe in Bytes, der dem String-Heap.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fbfb-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7fbfb-107">Requirements</span></span>  
 <span data-ttu-id="7fbfb-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fbfb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fbfb-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7fbfb-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fbfb-110">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7fbfb-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7fbfb-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fbfb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fbfb-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fbfb-112">See also</span></span>
- [<span data-ttu-id="7fbfb-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fbfb-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="7fbfb-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fbfb-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
