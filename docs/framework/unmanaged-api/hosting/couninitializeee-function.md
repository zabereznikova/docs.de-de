---
title: CoUninitializeEE-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoUninitializeEE
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoUninitializeEE
helpviewer_keywords: CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4125a76ae50a293e35e326f775500c06120420d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="couninitializeee-function"></a><span data-ttu-id="afb77-102">CoUninitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="afb77-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="afb77-103">`CoUninitializeEE`ist veraltet und stellt keine Funktionalität bereit.</span><span class="sxs-lookup"><span data-stu-id="afb77-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb77-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="afb77-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="afb77-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="afb77-105">Remarks</span></span>  
 <span data-ttu-id="afb77-106">Das Ausführungsmodul der common Language Runtime kann nicht aus einem Prozess entladen werden.</span><span class="sxs-lookup"><span data-stu-id="afb77-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="afb77-107">Beim Herunterfahren der Datenbankmodul-Ausführungsaufruf [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="afb77-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb77-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afb77-108">See Also</span></span>  
 [<span data-ttu-id="afb77-109">CoInitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="afb77-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 [<span data-ttu-id="afb77-110">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="afb77-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
