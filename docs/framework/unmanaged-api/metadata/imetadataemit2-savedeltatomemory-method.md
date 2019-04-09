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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa95a737747e9153eb844cddd8e0684585b9108b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081133"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="97e49-102">IMetaDataEmit2::SaveDeltaToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="97e49-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="97e49-103">Speichert Änderungen am Speicher aus der aktuellen Sitzung mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="97e49-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97e49-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97e49-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97e49-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="97e49-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="97e49-106">[out] Die Adresse, beginnen mit dem Erstellen des Metadatendeltas.</span><span class="sxs-lookup"><span data-stu-id="97e49-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="97e49-107">[in] Die Größe der Änderungen.</span><span class="sxs-lookup"><span data-stu-id="97e49-107">[in] The size of the changes.</span></span> <span data-ttu-id="97e49-108">Verwendung [IMetaDataEmit2:: GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) zur Bestimmung der Größe.</span><span class="sxs-lookup"><span data-stu-id="97e49-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97e49-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97e49-109">Requirements</span></span>  
 <span data-ttu-id="97e49-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97e49-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97e49-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="97e49-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="97e49-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="97e49-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="97e49-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="97e49-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="97e49-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97e49-114">See also</span></span>

- [<span data-ttu-id="97e49-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97e49-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="97e49-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97e49-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
