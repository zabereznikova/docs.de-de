---
title: IMetaDataEmit2::SaveDeltaToMemory-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: 8a6f11996425c92d9b0e3123ee2d3a064739454b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492755"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="38708-102">IMetaDataEmit2::SaveDeltaToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="38708-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="38708-103">Speichert Änderungen aus der aktuellen Bearbeitungs-und fortsetzungssitzung in den Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="38708-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38708-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38708-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38708-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="38708-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="38708-106">vorgenommen Die Adresse, an der mit dem Schreiben der metadatendelta begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="38708-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="38708-107">in Die Größe der Änderungen.</span><span class="sxs-lookup"><span data-stu-id="38708-107">[in] The size of the changes.</span></span> <span data-ttu-id="38708-108">Verwenden Sie [IMetaDataEmit2:: getdelta tasavesize](imetadataemit2-getdeltasavesize-method.md) , um die Größe zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="38708-108">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38708-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="38708-109">Requirements</span></span>  
 <span data-ttu-id="38708-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38708-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38708-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="38708-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38708-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="38708-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38708-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38708-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38708-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="38708-114">See also</span></span>

- [<span data-ttu-id="38708-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="38708-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="38708-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="38708-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
