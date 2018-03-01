---
title: CoUninitializeCor-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b9f50892b44cf8ce22cc126fe22323c8b0bbe6be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="couninitializecor-function"></a><span data-ttu-id="a8e3b-102">CoUninitializeCor-Funktion</span><span class="sxs-lookup"><span data-stu-id="a8e3b-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="a8e3b-103">`CoUninitializeCor` ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="a8e3b-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8e3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8e3b-104">Syntax</span></span>  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a8e3b-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8e3b-105">Remarks</span></span>  
 <span data-ttu-id="a8e3b-106">Die common Language Runtime kann nicht aus einem Prozess entladen werden.</span><span class="sxs-lookup"><span data-stu-id="a8e3b-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="a8e3b-107">Die Laufzeit von einem laufenden Prozess entfernen möchten, müssen Sie diesen Prozess herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="a8e3b-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e3b-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8e3b-108">See Also</span></span>  
 [<span data-ttu-id="a8e3b-109">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="a8e3b-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
