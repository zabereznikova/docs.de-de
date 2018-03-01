---
title: CorExitProcess-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 560f63c131ad336a3ff4b4edec0aed2b58d33ba5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corexitprocess-function"></a><span data-ttu-id="aca3a-102">CorExitProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="aca3a-102">CorExitProcess Function</span></span>
<span data-ttu-id="aca3a-103">Beendet den aktuellen nicht verwalteten Prozess.</span><span class="sxs-lookup"><span data-stu-id="aca3a-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="aca3a-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="aca3a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="aca3a-105">Verwenden der [ICLRMetaHost:: ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="aca3a-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aca3a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="aca3a-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aca3a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="aca3a-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="aca3a-108">Eine ganze Zahl, die Exitcode des Prozesses angibt.</span><span class="sxs-lookup"><span data-stu-id="aca3a-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aca3a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aca3a-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aca3a-110">Beginnend mit der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` jede gestartete Laufzeit im Prozess, nicht nur die Laufzeit, die an die die legacy-APIs gebunden wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="aca3a-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aca3a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aca3a-111">Requirements</span></span>  
 <span data-ttu-id="aca3a-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aca3a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aca3a-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aca3a-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aca3a-114">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="aca3a-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aca3a-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aca3a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca3a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aca3a-116">See Also</span></span>  
 [<span data-ttu-id="aca3a-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="aca3a-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
