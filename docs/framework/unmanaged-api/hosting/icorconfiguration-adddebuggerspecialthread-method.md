---
title: ICorConfiguration::AddDebuggerSpecialThread-Methode
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a73232fb9327880f0038097d71698ddf8bf005e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779907"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="33f41-102">ICorConfiguration::AddDebuggerSpecialThread-Methode</span><span class="sxs-lookup"><span data-stu-id="33f41-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="33f41-103">Zeigt das Debuggen von Diensten an, dass ein bestimmter Thread darf weiterhin ausgeführt, während der Debugger eine Anwendung, die während des Szenarios des verwalteten oder nicht verwalteten Debuggens beendet hat.</span><span class="sxs-lookup"><span data-stu-id="33f41-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33f41-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33f41-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33f41-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="33f41-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="33f41-106">[in] Die ID des Threads, der zugelassen werden soll, weiter ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="33f41-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33f41-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33f41-107">Remarks</span></span>  
 <span data-ttu-id="33f41-108">Der angegebene Thread wird nicht zulässig sein, um verwalteten Code ausführen, oder geben die Laufzeit in keiner Weise.</span><span class="sxs-lookup"><span data-stu-id="33f41-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="33f41-109">Ein Beispiel für einen solchen Thread wäre ein in-Process-Thread zur Unterstützung von legacy Skriptdebugger.</span><span class="sxs-lookup"><span data-stu-id="33f41-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33f41-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33f41-110">Requirements</span></span>  
 <span data-ttu-id="33f41-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33f41-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33f41-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33f41-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33f41-113">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="33f41-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33f41-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33f41-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f41-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33f41-115">See also</span></span>

- [<span data-ttu-id="33f41-116">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33f41-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
