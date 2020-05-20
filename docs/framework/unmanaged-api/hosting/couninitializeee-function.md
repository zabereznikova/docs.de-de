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
ms.openlocfilehash: fa6297e926d53c02bb0d1af7b59b45b8ee152399
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616462"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="b87a5-102">CoUninitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="b87a5-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="b87a5-103">`CoUninitializeEE`ist veraltet und bietet keine Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="b87a5-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b87a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b87a5-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="b87a5-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b87a5-105">Remarks</span></span>  
 <span data-ttu-id="b87a5-106">Die Common Language Runtime Ausführungs-Engine kann nicht aus einem Prozess entladen werden.</span><span class="sxs-lookup"><span data-stu-id="b87a5-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="b87a5-107">Zum Herunterfahren der Ausführungs-Engine wird [CorExitProcess](corexitprocess-function.md)aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b87a5-107">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b87a5-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b87a5-108">See also</span></span>

- [<span data-ttu-id="b87a5-109">CoInitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="b87a5-109">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="b87a5-110">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="b87a5-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
