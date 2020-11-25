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
ms.openlocfilehash: 5ae0a887d666a150b717d495848c8a411d030a09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728575"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="d8778-102">NukeDownloadedCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="d8778-102">NukeDownloadedCache Function</span></span>

<span data-ttu-id="d8778-103">Löscht den Common Language Runtime Download Cache (CLR).</span><span class="sxs-lookup"><span data-stu-id="d8778-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8778-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8778-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d8778-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d8778-105">Return Value</span></span>  

 <span data-ttu-id="d8778-106">Diese Methode gibt Standard-COM-Fehlercodes zurück, wie in WinError. h definiert.</span><span class="sxs-lookup"><span data-stu-id="d8778-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8778-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8778-107">Remarks</span></span>  

 <span data-ttu-id="d8778-108">Der CLR-Download Cache ist der Bereich, in dem Assemblys mit starkem Namen, die von einer URL heruntergeladen werden, zur möglichen Wiederverwendung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d8778-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8778-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d8778-109">Requirements</span></span>  

 <span data-ttu-id="d8778-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8778-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8778-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d8778-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d8778-112">**Bibliothek:** Fusion.dll und Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="d8778-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="d8778-113">Verwenden Sie Fusion.dll anstelle von Mscorwks.dll, um sicherzustellen, dass Sie die richtige Version der .NET Framework als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8778-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="d8778-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8778-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8778-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8778-115">See also</span></span>

- [<span data-ttu-id="d8778-116">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="d8778-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="d8778-117">GetHistoryFileDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="d8778-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="d8778-118">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="d8778-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
