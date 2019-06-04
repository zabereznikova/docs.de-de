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
ms.openlocfilehash: 2a28b33f80299ae6fce34f9de66b6f7f1bc70ef6
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490567"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="9e2f4-102">CorExitProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="9e2f4-102">CorExitProcess Function</span></span>
<span data-ttu-id="9e2f4-103">Beendet den aktuellen nicht verwalteten Prozess.</span><span class="sxs-lookup"><span data-stu-id="9e2f4-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="9e2f4-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="9e2f4-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="9e2f4-105">Verwenden der [ICLRMetaHost:: ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="9e2f4-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e2f4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e2f4-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e2f4-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e2f4-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="9e2f4-108">Eine ganze Zahl, die Exitcode des Prozesses angibt.</span><span class="sxs-lookup"><span data-stu-id="9e2f4-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e2f4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e2f4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e2f4-110">Ab .NET Framework 4, `CorExitProcess` jede gestartete Laufzeit im Prozess nicht nur die Laufzeit, die legacy-APIs gebunden wurden, beendet.</span><span class="sxs-lookup"><span data-stu-id="9e2f4-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e2f4-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e2f4-111">Requirements</span></span>  
 <span data-ttu-id="9e2f4-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e2f4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e2f4-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9e2f4-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e2f4-114">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9e2f4-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e2f4-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e2f4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e2f4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e2f4-116">See also</span></span>

- [<span data-ttu-id="9e2f4-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="9e2f4-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
