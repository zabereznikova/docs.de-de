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
ms.openlocfilehash: ce8d3356b1f9b73e33ed2d3215c7f8115e64ac70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426653"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="1e8ed-102">IMetaDataTables::GetUserStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="1e8ed-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="1e8ed-103">Ruft die Größe des Benutzer Zeichen folgen Heaps in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e8ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e8ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e8ed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e8ed-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="1e8ed-106">vorgenommen Ein Zeiger auf die Größe des Benutzer Zeichen folgen Heaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e8ed-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1e8ed-107">Requirements</span></span>  
 <span data-ttu-id="1e8ed-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e8ed-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e8ed-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1e8ed-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e8ed-110">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e8ed-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e8ed-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e8ed-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e8ed-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e8ed-112">See also</span></span>

- [<span data-ttu-id="1e8ed-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e8ed-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="1e8ed-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e8ed-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
