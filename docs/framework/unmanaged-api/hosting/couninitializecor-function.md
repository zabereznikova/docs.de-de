---
title: CoUninitializeCor-Funktion
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: 7d39c6fda6f159bfc937f62dc45d0d7ce37657f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687880"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="a1681-102">CoUninitializeCor-Funktion</span><span class="sxs-lookup"><span data-stu-id="a1681-102">CoUninitializeCor Function</span></span>

<span data-ttu-id="a1681-103">`CoUninitializeCor` ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="a1681-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1681-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1681-104">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a1681-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1681-105">Remarks</span></span>  

 <span data-ttu-id="a1681-106">Der Common Language Runtime kann nicht aus einem Prozess entladen werden.</span><span class="sxs-lookup"><span data-stu-id="a1681-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="a1681-107">Wenn Sie die Laufzeit vollständig aus einem laufenden Prozess entfernen möchten, müssen Sie diesen Prozess beenden.</span><span class="sxs-lookup"><span data-stu-id="a1681-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1681-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1681-108">See also</span></span>

- [<span data-ttu-id="a1681-109">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="a1681-109">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
