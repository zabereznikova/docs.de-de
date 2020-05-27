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
ms.openlocfilehash: 7ce9ac95c7183a7d47c367914d80f77c57dde0d7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005764"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="95f12-102">IMetaDataEmit::ApplyEditAndContinue-Methode</span><span class="sxs-lookup"><span data-stu-id="95f12-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="95f12-103">Aktualisiert den aktuellen Assemblybereich mit den Änderungen, die in den angegebenen Metadaten vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="95f12-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95f12-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95f12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="95f12-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="95f12-106">\[in \] Zeiger auf ein [IUnknown](/cpp/atl/iunknown) -Objekt, das die Delta Metadaten aus der portablen ausführbaren Datei (PE) darstellt.</span><span class="sxs-lookup"><span data-stu-id="95f12-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="95f12-107">Die Delta Metadaten sind der Metadatenblock, der die Änderungen enthält, die an der Kopie der eigentlichen Metadaten des Moduls vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="95f12-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95f12-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="95f12-108">Requirements</span></span>  
 <span data-ttu-id="95f12-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95f12-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f12-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="95f12-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95f12-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="95f12-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95f12-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95f12-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f12-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95f12-113">See also</span></span>

- [<span data-ttu-id="95f12-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95f12-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="95f12-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95f12-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
