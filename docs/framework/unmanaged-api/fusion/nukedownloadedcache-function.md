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
ms.openlocfilehash: 29f492173a7fd22ab497d6e0096798e164fccf26
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796304"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="e308b-102">NukeDownloadedCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="e308b-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="e308b-103">Löscht den Common Language Runtime Download Cache (CLR).</span><span class="sxs-lookup"><span data-stu-id="e308b-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e308b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e308b-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e308b-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e308b-105">Return Value</span></span>  
 <span data-ttu-id="e308b-106">Diese Methode gibt Standard-COM-Fehlercodes zurück, wie in WinError. h definiert.</span><span class="sxs-lookup"><span data-stu-id="e308b-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e308b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e308b-107">Remarks</span></span>  
 <span data-ttu-id="e308b-108">Der CLR-Download Cache ist der Bereich, in dem Assemblys mit starkem Namen, die von einer URL heruntergeladen werden, zur möglichen Wiederverwendung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e308b-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e308b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e308b-109">Requirements</span></span>  
 <span data-ttu-id="e308b-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e308b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e308b-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e308b-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e308b-112">**Fern** "Fusion. dll" und "mscorwert. dll".</span><span class="sxs-lookup"><span data-stu-id="e308b-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="e308b-113">Verwenden Sie "Fusion. dll" anstelle von "mscorwert. dll", um sicherzustellen, dass Sie die richtige Version des .NET Framework als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="e308b-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e308b-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e308b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e308b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e308b-115">See also</span></span>

- [<span data-ttu-id="e308b-116">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="e308b-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="e308b-117">GetHistoryFileDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="e308b-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="e308b-118">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="e308b-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
