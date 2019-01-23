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
ms.openlocfilehash: 84972388f90ea23032ed0524723d59077c732e59
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498894"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="9cf84-102">IMetaDataEmit2::SaveDeltaToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="9cf84-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="9cf84-103">Speichert Änderungen am Speicher aus der aktuellen Sitzung mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9cf84-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cf84-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cf84-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9cf84-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="9cf84-106">[out] Die Adresse, beginnen mit dem Erstellen des Metadatendeltas.</span><span class="sxs-lookup"><span data-stu-id="9cf84-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="9cf84-107">[in] Die Größe der Änderungen.</span><span class="sxs-lookup"><span data-stu-id="9cf84-107">[in] The size of the changes.</span></span> <span data-ttu-id="9cf84-108">Verwendung [IMetaDataEmit2:: GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) zur Bestimmung der Größe.</span><span class="sxs-lookup"><span data-stu-id="9cf84-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cf84-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9cf84-109">Requirements</span></span>  
 <span data-ttu-id="9cf84-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cf84-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cf84-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9cf84-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9cf84-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9cf84-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9cf84-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cf84-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf84-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cf84-114">See also</span></span>
- [<span data-ttu-id="9cf84-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9cf84-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="9cf84-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9cf84-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
