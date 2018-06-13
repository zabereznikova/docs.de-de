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
ms.openlocfilehash: a217a835e258052ace5b59a70cbc0fa31691d78e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452845"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="a139c-102">IMetaDataTables::GetUserStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="a139c-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="a139c-103">Ruft die Größe des dem Benutzer String-Heap in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="a139c-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a139c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a139c-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a139c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a139c-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="a139c-106">[out] Ein Zeiger auf die Größe in Bytes, der dem Benutzer String-Heap.</span><span class="sxs-lookup"><span data-stu-id="a139c-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a139c-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a139c-107">Requirements</span></span>  
 <span data-ttu-id="a139c-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a139c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a139c-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a139c-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a139c-110">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a139c-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a139c-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a139c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a139c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a139c-112">See Also</span></span>  
 [<span data-ttu-id="a139c-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a139c-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="a139c-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a139c-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
