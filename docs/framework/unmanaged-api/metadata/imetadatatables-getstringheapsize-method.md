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
ms.openlocfilehash: e3f6afaa79b7b299fa374c8220f5c2c3ad545ac9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672559"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="1c2eb-102">IMetaDataTables::GetStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="1c2eb-102">IMetaDataTables::GetStringHeapSize Method</span></span>

<span data-ttu-id="1c2eb-103">Ruft die Größe des Zeichen folgen Heaps in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c2eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c2eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c2eb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c2eb-105">Parameters</span></span>  

 `pcbStrings`  
 <span data-ttu-id="1c2eb-106">vorgenommen Ein Zeiger auf die Größe des Zeichen folgen Heaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c2eb-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1c2eb-107">Requirements</span></span>  

 <span data-ttu-id="1c2eb-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c2eb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c2eb-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1c2eb-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c2eb-110">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c2eb-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c2eb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c2eb-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1c2eb-112">See also</span></span>

- [<span data-ttu-id="1c2eb-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c2eb-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="1c2eb-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c2eb-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
