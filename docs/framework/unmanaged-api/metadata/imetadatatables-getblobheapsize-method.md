---
title: IMetaDataTables::GetBlobHeapSize-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
ms.openlocfilehash: e508bcae15e72ce592529cf4b68af5d75ea49038
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721958"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="a9a45-102">IMetaDataTables::GetBlobHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="a9a45-102">IMetaDataTables::GetBlobHeapSize Method</span></span>

<span data-ttu-id="a9a45-103">Ruft die Größe des Binary Large Object (BLOB)-Heaps in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="a9a45-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9a45-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9a45-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="a9a45-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9a45-105">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="a9a45-106">vorgenommen Ein Zeiger auf die Größe des BLOB-Heaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="a9a45-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9a45-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a9a45-107">Requirements</span></span>  

 <span data-ttu-id="a9a45-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9a45-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9a45-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a9a45-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9a45-110">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9a45-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9a45-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9a45-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a45-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9a45-112">See also</span></span>

- [<span data-ttu-id="a9a45-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9a45-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="a9a45-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9a45-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
