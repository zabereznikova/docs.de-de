---
title: NukeDownloadedCache-Funktion
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76ada8400573dd61c25e0dce3f49ce66b5fb30c1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773799"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="ef095-102">NukeDownloadedCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="ef095-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="ef095-103">Löscht den Downloadcache der common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ef095-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef095-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef095-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ef095-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ef095-105">Return Value</span></span>  
 <span data-ttu-id="ef095-106">Diese Methode gibt die standard-COM-Fehlercodes, in WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="ef095-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef095-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef095-107">Remarks</span></span>  
 <span data-ttu-id="ef095-108">Der CLR-Downloadcache ist der Bereich, in dem Assemblys mit starkem Namen, die von einer URL heruntergeladen werden für die mögliche Wiederverwendung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ef095-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef095-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef095-109">Requirements</span></span>  
 <span data-ttu-id="ef095-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef095-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef095-111">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ef095-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ef095-112">**Bibliothek:** Fusion.dll und "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="ef095-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="ef095-113">Verwenden Sie Fusion.dll anstelle von "Mscorwks.dll", um sicherzustellen, dass Sie die richtige Version von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="ef095-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ef095-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef095-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef095-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef095-115">See also</span></span>

- [<span data-ttu-id="ef095-116">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="ef095-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="ef095-117">GetHistoryFileDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="ef095-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [<span data-ttu-id="ef095-118">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="ef095-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
