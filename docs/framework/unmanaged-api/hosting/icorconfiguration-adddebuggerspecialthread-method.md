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
ms.openlocfilehash: db1b19c1499f7e8a126933b4d0635a0ab73e72a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218588"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="8e5b5-102">ICorConfiguration::AddDebuggerSpecialThread-Methode</span><span class="sxs-lookup"><span data-stu-id="8e5b5-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="8e5b5-103">Zeigt das Debuggen von Diensten an, dass ein bestimmter Thread darf weiterhin ausgeführt, während der Debugger eine Anwendung, die während des Szenarios des verwalteten oder nicht verwalteten Debuggens beendet hat.</span><span class="sxs-lookup"><span data-stu-id="8e5b5-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e5b5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e5b5-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e5b5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8e5b5-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="8e5b5-106">[in] Die ID des Threads, der zugelassen werden soll, weiter ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8e5b5-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e5b5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e5b5-107">Remarks</span></span>  
 <span data-ttu-id="8e5b5-108">Der angegebene Thread wird nicht zulässig sein, um verwalteten Code ausführen, oder geben die Laufzeit in keiner Weise.</span><span class="sxs-lookup"><span data-stu-id="8e5b5-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="8e5b5-109">Ein Beispiel für einen solchen Thread wäre ein in-Process-Thread zur Unterstützung von legacy Skriptdebugger.</span><span class="sxs-lookup"><span data-stu-id="8e5b5-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e5b5-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e5b5-110">Requirements</span></span>  
 <span data-ttu-id="8e5b5-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e5b5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e5b5-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e5b5-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e5b5-113">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8e5b5-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e5b5-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e5b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5b5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e5b5-115">See also</span></span>

- [<span data-ttu-id="8e5b5-116">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e5b5-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
