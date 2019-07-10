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
ms.openlocfilehash: 79b21613ba844ca4c749d9c04d75260e326e6512
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777132"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="3310f-102">IMetaDataEmit2::SaveDeltaToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="3310f-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="3310f-103">Speichert Änderungen am Speicher aus der aktuellen Sitzung mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3310f-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3310f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3310f-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3310f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3310f-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="3310f-106">[out] Die Adresse, beginnen mit dem Erstellen des Metadatendeltas.</span><span class="sxs-lookup"><span data-stu-id="3310f-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="3310f-107">[in] Die Größe der Änderungen.</span><span class="sxs-lookup"><span data-stu-id="3310f-107">[in] The size of the changes.</span></span> <span data-ttu-id="3310f-108">Verwendung [IMetaDataEmit2:: GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) zur Bestimmung der Größe.</span><span class="sxs-lookup"><span data-stu-id="3310f-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3310f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3310f-109">Requirements</span></span>  
 <span data-ttu-id="3310f-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3310f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3310f-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3310f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3310f-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="3310f-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3310f-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3310f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3310f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3310f-114">See also</span></span>

- [<span data-ttu-id="3310f-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3310f-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="3310f-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3310f-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
