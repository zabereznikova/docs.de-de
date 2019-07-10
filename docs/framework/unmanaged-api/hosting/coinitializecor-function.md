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
ms.openlocfilehash: 7b2b7b89c73b59f4f735369659daabb6a8f88300
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779094"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="70842-102">CoInitializeCor-Funktion</span><span class="sxs-lookup"><span data-stu-id="70842-102">CoInitializeCor Function</span></span>
<span data-ttu-id="70842-103">`CoInitializeCor` ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="70842-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70842-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="70842-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="70842-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70842-105">Remarks</span></span>  
 <span data-ttu-id="70842-106">Verwenden Sie zum Initialisieren der common Language Runtime entweder [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="70842-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70842-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70842-107">Requirements</span></span>  
 <span data-ttu-id="70842-108">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="70842-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70842-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70842-109">See also</span></span>

- [<span data-ttu-id="70842-110">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="70842-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
