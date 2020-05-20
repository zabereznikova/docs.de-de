---
title: CorExitProcess-Funktion
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: a60805e1fd78cb14835957a7afc14fe279cb20fb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616566"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="cea41-102">CorExitProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="cea41-102">CorExitProcess Function</span></span>
<span data-ttu-id="cea41-103">Beendet den aktuellen nicht verwalteten Prozess.</span><span class="sxs-lookup"><span data-stu-id="cea41-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="cea41-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="cea41-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="cea41-105">Verwenden Sie stattdessen die [ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="cea41-105">Use the [ICLRMetaHost::ExitProcess](iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cea41-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="cea41-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cea41-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="cea41-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="cea41-108">Eine ganze Zahl, die den Prozessexitcode angibt.</span><span class="sxs-lookup"><span data-stu-id="cea41-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cea41-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cea41-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cea41-110">Beginnend mit dem .NET Framework 4 wird `CorExitProcess` jede gestartete Laufzeit im Prozess beendet, nicht nur die Laufzeit, an die die Legacy-APIs gebunden wurden.</span><span class="sxs-lookup"><span data-stu-id="cea41-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cea41-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cea41-111">Requirements</span></span>  
 <span data-ttu-id="cea41-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cea41-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cea41-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="cea41-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cea41-114">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cea41-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cea41-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cea41-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cea41-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cea41-116">See also</span></span>

- [<span data-ttu-id="cea41-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="cea41-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
