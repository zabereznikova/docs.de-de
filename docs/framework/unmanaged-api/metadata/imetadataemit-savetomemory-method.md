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
ms.openlocfilehash: bc840df9dd0793a7347b7f0d8a05296a09d634c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192107"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="6ebce-102">IMetaDataEmit::SaveToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="6ebce-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="6ebce-103">Speichert alle Metadaten im aktuellen Bereich in den angegebenen Bereich des Arbeitsspeichers an.</span><span class="sxs-lookup"><span data-stu-id="6ebce-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ebce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ebce-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ebce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ebce-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="6ebce-106">[out] Die Adresse, an dem beginnt beim Schreiben der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="6ebce-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="6ebce-107">[in] Die Größe des belegten Arbeitsspeichers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="6ebce-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ebce-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ebce-108">Requirements</span></span>  
 <span data-ttu-id="6ebce-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ebce-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ebce-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6ebce-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ebce-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="6ebce-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6ebce-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6ebce-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ebce-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ebce-113">See also</span></span>

- [<span data-ttu-id="6ebce-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ebce-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6ebce-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ebce-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
