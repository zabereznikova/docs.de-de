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
ms.openlocfilehash: 80891da7d61aa5114d5cc4d8aff4c7ce82020237
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720092"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="607da-102">NukeDownloadedCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="607da-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="607da-103">Löscht den Downloadcache der common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="607da-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="607da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="607da-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="607da-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="607da-105">Return Value</span></span>  
 <span data-ttu-id="607da-106">Diese Methode gibt die standard-COM-Fehlercodes, in WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="607da-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="607da-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="607da-107">Remarks</span></span>  
 <span data-ttu-id="607da-108">Der CLR-Downloadcache ist der Bereich, in dem Assemblys mit starkem Namen, die von einer URL heruntergeladen werden für die mögliche Wiederverwendung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="607da-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="607da-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="607da-109">Requirements</span></span>  
 <span data-ttu-id="607da-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="607da-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="607da-111">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="607da-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="607da-112">**Bibliothek:** Fusion.dll und "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="607da-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="607da-113">Verwenden Sie Fusion.dll anstelle von "Mscorwks.dll", um sicherzustellen, dass Sie die richtige Version von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="607da-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="607da-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="607da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="607da-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="607da-115">See also</span></span>
- [<span data-ttu-id="607da-116">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="607da-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="607da-117">GetHistoryFileDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="607da-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [<span data-ttu-id="607da-118">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="607da-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
