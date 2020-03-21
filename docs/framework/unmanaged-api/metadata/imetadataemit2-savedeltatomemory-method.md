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
ms.openlocfilehash: 5ec4fe2a8e949cf6e9aa0ce68f4d4e49b72170b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177439"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="8525a-102">IMetaDataEmit2::SaveDeltaToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="8525a-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="8525a-103">Speichert Änderungen aus der aktuellen Bearbeitungs- und Fortsetzungssitzung im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="8525a-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8525a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8525a-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8525a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8525a-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="8525a-106">[out] Die Adresse, unter der mit dem Schreiben des Metadatendeltas begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="8525a-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="8525a-107">[in] Die Größe der Änderungen.</span><span class="sxs-lookup"><span data-stu-id="8525a-107">[in] The size of the changes.</span></span> <span data-ttu-id="8525a-108">Verwenden Sie [IMetaDataEmit2::GetDeltaSaveSize,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) um die Größe zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="8525a-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8525a-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8525a-109">Requirements</span></span>  
 <span data-ttu-id="8525a-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8525a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8525a-111">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8525a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8525a-112">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="8525a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8525a-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8525a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8525a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8525a-114">See also</span></span>

- [<span data-ttu-id="8525a-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8525a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="8525a-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8525a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
