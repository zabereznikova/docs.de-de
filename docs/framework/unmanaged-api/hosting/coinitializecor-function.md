---
title: CoInitializeCor-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoInitializeCor
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoInitializeCor
helpviewer_keywords: CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 119a01a33faeedc49931f3e7cbb1685b26366d0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="coinitializecor-function"></a><span data-ttu-id="ffbad-102">CoInitializeCor-Funktion</span><span class="sxs-lookup"><span data-stu-id="ffbad-102">CoInitializeCor Function</span></span>
<span data-ttu-id="ffbad-103">`CoInitializeCor` ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="ffbad-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffbad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ffbad-104">Syntax</span></span>  
  
```  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="ffbad-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ffbad-105">Remarks</span></span>  
 <span data-ttu-id="ffbad-106">Verwenden Sie zum Initialisieren der common Language Runtime entweder [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="ffbad-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffbad-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ffbad-107">Requirements</span></span>  
 <span data-ttu-id="ffbad-108">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ffbad-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffbad-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffbad-109">See Also</span></span>  
 [<span data-ttu-id="ffbad-110">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="ffbad-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
