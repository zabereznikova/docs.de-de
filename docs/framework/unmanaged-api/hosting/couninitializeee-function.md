---
title: CoUninitializeEE-Funktion
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
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
ms.openlocfilehash: d05bc472711838236ed18b00ce808d022d9581dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758199"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="fb07a-102">CoUninitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="fb07a-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="fb07a-103">`CoUninitializeEE` ist veraltet, und stellt keine Funktionalität bereit.</span><span class="sxs-lookup"><span data-stu-id="fb07a-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb07a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb07a-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="fb07a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb07a-105">Remarks</span></span>  
 <span data-ttu-id="fb07a-106">Die common Language Runtime ausführungs-Engine kann nicht von einem Prozess entladen werden.</span><span class="sxs-lookup"><span data-stu-id="fb07a-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="fb07a-107">Herunterfahren der Engine Ausführungsaufruf [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="fb07a-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb07a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb07a-108">See also</span></span>

- [<span data-ttu-id="fb07a-109">CoInitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="fb07a-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="fb07a-110">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="fb07a-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
