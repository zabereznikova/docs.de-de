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
ms.openlocfilehash: c5d6cfa3826667514eb70f9bb0df118d9ba0d07c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127822"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="9b682-102">ICorConfiguration::AddDebuggerSpecialThread-Methode</span><span class="sxs-lookup"><span data-stu-id="9b682-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="9b682-103">Gibt den Debugdiensten an, dass ein bestimmter Thread weiter ausgeführt werden darf, während der Debugger eine Anwendung während verwalteter oder nicht verwalteter debuggingszenarien beendet hat.</span><span class="sxs-lookup"><span data-stu-id="9b682-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b682-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b682-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b682-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b682-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="9b682-106">in Die ID des Threads, der zugelassen werden soll, dass die Ausführung fortgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b682-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b682-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b682-107">Remarks</span></span>  
 <span data-ttu-id="9b682-108">Der angegebene Thread darf keinen verwalteten Code ausführen oder die Laufzeit in irgendeiner Weise eingeben.</span><span class="sxs-lookup"><span data-stu-id="9b682-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="9b682-109">Ein Beispiel für einen solchen Thread wäre ein Prozess interner Thread, der Legacy-Skript-debuggger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9b682-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b682-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b682-110">Requirements</span></span>  
 <span data-ttu-id="9b682-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b682-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b682-112">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9b682-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b682-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9b682-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b682-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b682-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b682-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b682-115">See also</span></span>

- [<span data-ttu-id="9b682-116">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b682-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
