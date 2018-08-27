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
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930936"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="9b78e-102">IMetaDataEmit::ApplyEditAndContinue-Methode</span><span class="sxs-lookup"><span data-stu-id="9b78e-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="9b78e-103">Aktualisiert den aktuellen Assemblybereich mit den Änderungen in den angegebenen Metadaten.</span><span class="sxs-lookup"><span data-stu-id="9b78e-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b78e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b78e-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b78e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b78e-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="9b78e-106">\[in\] Zeiger auf ein [IUnknown](/cpp/atl/iunknown) Objekt, das die Deltametadaten aus der Datei (portable Executable)-Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="9b78e-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="9b78e-107">Die Deltametadaten ist der Block von Metadaten mit den Änderungen, die auf die Kopie des Moduls eigentlichen Metadaten vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="9b78e-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b78e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b78e-108">Requirements</span></span>  
 <span data-ttu-id="9b78e-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b78e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b78e-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b78e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b78e-111">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9b78e-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b78e-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b78e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b78e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b78e-113">See Also</span></span>  
 [<span data-ttu-id="9b78e-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b78e-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9b78e-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b78e-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
