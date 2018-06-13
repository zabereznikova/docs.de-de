---
title: CoUninitializeEE-Funktion
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73fa281d28e9b5362ff386b55b07dd431f1915f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429181"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="425de-102">CoUninitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="425de-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="425de-103">`CoUninitializeEE` ist veraltet und stellt keine Funktionalität bereit.</span><span class="sxs-lookup"><span data-stu-id="425de-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="425de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="425de-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="425de-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="425de-105">Remarks</span></span>  
 <span data-ttu-id="425de-106">Das Ausführungsmodul der common Language Runtime kann nicht aus einem Prozess entladen werden.</span><span class="sxs-lookup"><span data-stu-id="425de-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="425de-107">Beim Herunterfahren der Datenbankmodul-Ausführungsaufruf [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="425de-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="425de-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="425de-108">See Also</span></span>  
 [<span data-ttu-id="425de-109">CoInitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="425de-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 [<span data-ttu-id="425de-110">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="425de-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
