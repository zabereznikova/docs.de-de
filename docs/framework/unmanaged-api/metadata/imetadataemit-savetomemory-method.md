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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3ef09c98f22b03a9c4473505605f1688d4bbf17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612228"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="f2191-102">IMetaDataEmit::SaveToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="f2191-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="f2191-103">Speichert alle Metadaten im aktuellen Bereich in den angegebenen Bereich des Arbeitsspeichers an.</span><span class="sxs-lookup"><span data-stu-id="f2191-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2191-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2191-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2191-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2191-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="f2191-106">[out] Die Adresse, an dem beginnt beim Schreiben der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="f2191-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="f2191-107">[in] Die Größe des belegten Arbeitsspeichers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f2191-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2191-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f2191-108">Requirements</span></span>  
 <span data-ttu-id="f2191-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2191-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2191-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2191-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2191-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f2191-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2191-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2191-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2191-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2191-113">See also</span></span>
- [<span data-ttu-id="f2191-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2191-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f2191-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2191-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
