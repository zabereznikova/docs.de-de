---
title: ICorConfiguration::AddDebuggerSpecialThread-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.AddDebuggerSpecialThread
api_location: mscoree.dll
api_type: COM
f1_keywords: AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2501461267ff7369cd9c48f4cef6cda42063a48b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="c0444-102">ICorConfiguration::AddDebuggerSpecialThread-Methode</span><span class="sxs-lookup"><span data-stu-id="c0444-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="c0444-103">Zeigt den Debugdiensten an, dass ein bestimmter Thread fortgesetzt werden, während der Debugger eine Anwendung, die während des Szenarios des verwalteten oder nicht verwalteten Debuggens beendet hat darf.</span><span class="sxs-lookup"><span data-stu-id="c0444-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0444-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0444-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0444-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0444-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="c0444-106">[in] Die ID des Threads, die ursprungsübergreifende weiterhin ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c0444-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0444-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c0444-107">Remarks</span></span>  
 <span data-ttu-id="c0444-108">Der angegebene Thread ist nicht möglich, verwalteten Code ausführen, oder geben die Laufzeit in keiner Weise.</span><span class="sxs-lookup"><span data-stu-id="c0444-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="c0444-109">Ein Beispiel für einen solchen Thread wäre ein in-Process-Thread zur Unterstützung von legacy Skriptdebugger.</span><span class="sxs-lookup"><span data-stu-id="c0444-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0444-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0444-110">Requirements</span></span>  
 <span data-ttu-id="c0444-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0444-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0444-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c0444-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0444-113">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c0444-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0444-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0444-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0444-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0444-115">See Also</span></span>  
 [<span data-ttu-id="c0444-116">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0444-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
