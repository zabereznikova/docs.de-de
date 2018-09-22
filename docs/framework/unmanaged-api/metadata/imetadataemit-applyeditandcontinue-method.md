---
title: IMetaDataEmit::ApplyEditAndContinue-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.ApplyEditAndContinue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: faa9bc412e67e0e49ee969bd8b246a424fe628a0
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46583901"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="6b3b3-102">IMetaDataEmit::ApplyEditAndContinue-Methode</span><span class="sxs-lookup"><span data-stu-id="6b3b3-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="6b3b3-103">Aktualisiert den aktuellen Assemblybereich mit den Änderungen in den angegebenen Metadaten.</span><span class="sxs-lookup"><span data-stu-id="6b3b3-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b3b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b3b3-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b3b3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b3b3-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="6b3b3-106">\[in\] Zeiger auf ein [IUnknown](/cpp/atl/iunknown) Objekt, das die Deltametadaten aus der Datei (portable Executable)-Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="6b3b3-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="6b3b3-107">Die Deltametadaten ist der Block von Metadaten mit den Änderungen, die auf die Kopie des Moduls eigentlichen Metadaten vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="6b3b3-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b3b3-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b3b3-108">Requirements</span></span>  
 <span data-ttu-id="6b3b3-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b3b3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b3b3-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6b3b3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b3b3-111">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="6b3b3-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b3b3-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b3b3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b3b3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b3b3-113">See Also</span></span>  
 [<span data-ttu-id="6b3b3-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b3b3-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="6b3b3-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b3b3-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
