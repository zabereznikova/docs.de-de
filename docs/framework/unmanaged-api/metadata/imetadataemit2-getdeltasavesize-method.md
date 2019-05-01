---
title: IMetaDataEmit2::GetDeltaSaveSize-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69897a7b646eb9f58e6b38588e302287b4241779
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043679"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="adbd1-102">IMetaDataEmit2::GetDeltaSaveSize-Methode</span><span class="sxs-lookup"><span data-stu-id="adbd1-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="adbd1-103">Ruft einen Wert, der angibt, jede Änderung in der Größe der Metadaten, die sich aus der aktuellen Sitzung mit bearbeiten und Fortfahren ergibt.</span><span class="sxs-lookup"><span data-stu-id="adbd1-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adbd1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="adbd1-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adbd1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="adbd1-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="adbd1-106">[in] Eines der [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) Werte, der gewünschten Genauigkeitsgrad angibt.</span><span class="sxs-lookup"><span data-stu-id="adbd1-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="adbd1-107">Bei .NET Framework, Version 2.0 wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="adbd1-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="adbd1-108">[out] Das Ändern der Größe der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="adbd1-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adbd1-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="adbd1-109">Requirements</span></span>  
 <span data-ttu-id="adbd1-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adbd1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adbd1-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="adbd1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="adbd1-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="adbd1-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="adbd1-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adbd1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adbd1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adbd1-114">See also</span></span>

- [<span data-ttu-id="adbd1-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="adbd1-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="adbd1-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="adbd1-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
