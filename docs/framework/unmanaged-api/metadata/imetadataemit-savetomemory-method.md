---
title: IMetaDataEmit::SaveToMemory-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
ms.openlocfilehash: 1cd5e34d6afefab2fda7e20d4bf73b373ad42787
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688587"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="21a7d-102">IMetaDataEmit::SaveToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="21a7d-102">IMetaDataEmit::SaveToMemory Method</span></span>

<span data-ttu-id="21a7d-103">Speichert alle Metadaten im aktuellen Gültigkeitsbereich im angegebenen Speicherbereich.</span><span class="sxs-lookup"><span data-stu-id="21a7d-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a7d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21a7d-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21a7d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21a7d-105">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="21a7d-106">vorgenommen Die Adresse, an der mit dem Schreiben von Metadaten begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="21a7d-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="21a7d-107">in Die Größe des zugeordneten Arbeitsspeichers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="21a7d-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21a7d-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="21a7d-108">Requirements</span></span>  

 <span data-ttu-id="21a7d-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21a7d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21a7d-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="21a7d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21a7d-111">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="21a7d-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21a7d-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21a7d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a7d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21a7d-113">See also</span></span>

- [<span data-ttu-id="21a7d-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21a7d-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="21a7d-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21a7d-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
