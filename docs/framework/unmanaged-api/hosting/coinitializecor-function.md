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
ms.openlocfilehash: 188f98504fa73c4a85615a4e688bae02d966b9b6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616748"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="9a2fe-102">CoInitializeCor-Funktion</span><span class="sxs-lookup"><span data-stu-id="9a2fe-102">CoInitializeCor Function</span></span>
<span data-ttu-id="9a2fe-103">`CoInitializeCor` ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="9a2fe-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a2fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a2fe-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="9a2fe-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a2fe-105">Remarks</span></span>  
 <span data-ttu-id="9a2fe-106">Um die Common Language Runtime zu initialisieren, verwenden Sie entweder [corbindtoriuntimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [corbindtoken currentruntime](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="9a2fe-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a2fe-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a2fe-107">Requirements</span></span>  
 <span data-ttu-id="9a2fe-108">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9a2fe-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a2fe-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a2fe-109">See also</span></span>

- [<span data-ttu-id="9a2fe-110">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="9a2fe-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
