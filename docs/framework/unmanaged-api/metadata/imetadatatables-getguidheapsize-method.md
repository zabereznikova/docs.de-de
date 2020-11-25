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
ms.openlocfilehash: 1b524067ac72dfd3bd19475f11d4ec12a307731d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702419"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="26e6c-102">IMetaDataTables::GetGuidHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="26e6c-102">IMetaDataTables::GetGuidHeapSize Method</span></span>

<span data-ttu-id="26e6c-103">Ruft die Größe des GUID-Heaps in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="26e6c-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26e6c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26e6c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="26e6c-105">Parameters</span></span>  

 `pcbGuids`  
 <span data-ttu-id="26e6c-106">vorgenommen Ein Zeiger auf die Größe des GUID-Heaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="26e6c-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26e6c-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="26e6c-107">Requirements</span></span>  

 <span data-ttu-id="26e6c-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26e6c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26e6c-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="26e6c-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26e6c-110">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="26e6c-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="26e6c-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26e6c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e6c-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26e6c-112">See also</span></span>

- [<span data-ttu-id="26e6c-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26e6c-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="26e6c-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26e6c-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
