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
ms.openlocfilehash: 38d0d794cdedfd058b93785f4f444b4dd3196195
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444769"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="47021-102">IMetaDataEmit2::SaveDeltaToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="47021-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="47021-103">Speichert Änderungen am Speicher aus der aktuellen Sitzung mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="47021-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47021-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47021-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47021-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="47021-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="47021-106">[out] Die Adresse, an dem Schreiben des Metadatendeltas beginnt.</span><span class="sxs-lookup"><span data-stu-id="47021-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="47021-107">[in] Die Größe der Änderungen.</span><span class="sxs-lookup"><span data-stu-id="47021-107">[in] The size of the changes.</span></span> <span data-ttu-id="47021-108">Verwendung [IMetaDataEmit2:: GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) zur Bestimmung der Größe.</span><span class="sxs-lookup"><span data-stu-id="47021-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47021-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47021-109">Requirements</span></span>  
 <span data-ttu-id="47021-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47021-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47021-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="47021-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47021-112">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="47021-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47021-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47021-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47021-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47021-114">See Also</span></span>  
 [<span data-ttu-id="47021-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47021-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="47021-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47021-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
