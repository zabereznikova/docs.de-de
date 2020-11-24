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
ms.openlocfilehash: 048010f00f6581a29c6b1a3150bf5ae8822b5664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672460"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="ef14c-102">IMetaDataTables::GetUserStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="ef14c-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>

<span data-ttu-id="ef14c-103">Ruft die Größe des Benutzer Zeichen folgen Heaps in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="ef14c-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef14c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef14c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef14c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef14c-105">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="ef14c-106">vorgenommen Ein Zeiger auf die Größe des Benutzer Zeichen folgen Heaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="ef14c-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef14c-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ef14c-107">Requirements</span></span>  

 <span data-ttu-id="ef14c-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef14c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef14c-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ef14c-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef14c-110">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef14c-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef14c-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef14c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef14c-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef14c-112">See also</span></span>

- [<span data-ttu-id="ef14c-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef14c-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="ef14c-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef14c-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
