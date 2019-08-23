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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e1104a98afb32dea687949e9c723124014c1e62
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925317"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="fcaed-102">CorExitProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="fcaed-102">CorExitProcess Function</span></span>
<span data-ttu-id="fcaed-103">Beendet den aktuellen nicht verwalteten Prozess.</span><span class="sxs-lookup"><span data-stu-id="fcaed-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="fcaed-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="fcaed-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="fcaed-105">Verwenden Sie stattdessen die [ICLRMetaHost:: ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="fcaed-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcaed-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcaed-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcaed-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="fcaed-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="fcaed-108">Eine ganze Zahl, die den Prozessexitcode angibt.</span><span class="sxs-lookup"><span data-stu-id="fcaed-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcaed-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcaed-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fcaed-110">Beginnend mit dem .NET Framework 4 wird `CorExitProcess` jede gestartete Laufzeit im Prozess beendet, nicht nur die Laufzeit, an die die Legacy-APIs gebunden wurden.</span><span class="sxs-lookup"><span data-stu-id="fcaed-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcaed-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fcaed-111">Requirements</span></span>  
 <span data-ttu-id="fcaed-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcaed-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcaed-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fcaed-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcaed-114">**Fern** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fcaed-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcaed-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcaed-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcaed-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcaed-116">See also</span></span>

- [<span data-ttu-id="fcaed-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="fcaed-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
