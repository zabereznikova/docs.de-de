---
title: IMetaDataEmit::Save-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90ddc540115a60154953ac6e8cb931103a650752
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492412"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="2f2d3-102">IMetaDataEmit::Save-Methode</span><span class="sxs-lookup"><span data-stu-id="2f2d3-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="2f2d3-103">Speichert alle Metadaten im aktuellen Bereich in die Datei an der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="2f2d3-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f2d3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f2d3-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f2d3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f2d3-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="2f2d3-106">[in] Der Name der Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2f2d3-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="2f2d3-107">Wenn dieser Wert null ist, wird der in-Memory-Kopie mit dem letzten Speicherort gespeichert, der verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2f2d3-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="2f2d3-108">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="2f2d3-108">[in] Reserved.</span></span> <span data-ttu-id="2f2d3-109">NULL muss sein.</span><span class="sxs-lookup"><span data-stu-id="2f2d3-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f2d3-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f2d3-110">Requirements</span></span>  
 <span data-ttu-id="2f2d3-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f2d3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f2d3-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2f2d3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f2d3-113">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2f2d3-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f2d3-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f2d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f2d3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f2d3-115">See also</span></span>
- [<span data-ttu-id="2f2d3-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f2d3-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2f2d3-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f2d3-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
