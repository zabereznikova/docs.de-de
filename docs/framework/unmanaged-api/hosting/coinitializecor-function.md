---
title: CoInitializeCor-Funktion
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8642c165c29f9ca63535a0efbb9dbb58d4660a49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160393"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="bead6-102">CoInitializeCor-Funktion</span><span class="sxs-lookup"><span data-stu-id="bead6-102">CoInitializeCor Function</span></span>
<span data-ttu-id="bead6-103">`CoInitializeCor` ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="bead6-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bead6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bead6-104">Syntax</span></span>  
  
```  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="bead6-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bead6-105">Remarks</span></span>  
 <span data-ttu-id="bead6-106">Verwenden Sie zum Initialisieren der common Language Runtime entweder [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="bead6-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bead6-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bead6-107">Requirements</span></span>  
 <span data-ttu-id="bead6-108">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bead6-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bead6-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bead6-109">See also</span></span>

- [<span data-ttu-id="bead6-110">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="bead6-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
