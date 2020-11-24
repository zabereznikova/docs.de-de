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
ms.openlocfilehash: e6616392eaa23f8ba40247c5aabd12e4d530cea1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687846"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="60961-102">CoUninitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="60961-102">CoUninitializeEE Function</span></span>

<span data-ttu-id="60961-103">`CoUninitializeEE` ist veraltet und bietet keine Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="60961-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60961-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60961-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="60961-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60961-105">Remarks</span></span>  

 <span data-ttu-id="60961-106">Die Common Language Runtime Ausführungs-Engine kann nicht aus einem Prozess entladen werden.</span><span class="sxs-lookup"><span data-stu-id="60961-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="60961-107">Zum Herunterfahren der Ausführungs-Engine wird [CorExitProcess](corexitprocess-function.md)aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="60961-107">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60961-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60961-108">See also</span></span>

- [<span data-ttu-id="60961-109">CoInitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="60961-109">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="60961-110">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="60961-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
