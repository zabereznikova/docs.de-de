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
ms.openlocfilehash: 8b6593ad995872f0e0014b1e8bcd8a4b576bbeaf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762426"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="4b666-102">ICorConfiguration::AddDebuggerSpecialThread-Methode</span><span class="sxs-lookup"><span data-stu-id="4b666-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="4b666-103">Gibt den Debugdiensten an, dass ein bestimmter Thread weiter ausgeführt werden darf, während der Debugger eine Anwendung während verwalteter oder nicht verwalteter debuggingszenarien beendet hat.</span><span class="sxs-lookup"><span data-stu-id="4b666-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b666-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b666-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b666-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b666-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="4b666-106">in Die ID des Threads, der zugelassen werden soll, dass die Ausführung fortgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4b666-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b666-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b666-107">Remarks</span></span>  
 <span data-ttu-id="4b666-108">Der angegebene Thread darf keinen verwalteten Code ausführen oder die Laufzeit in irgendeiner Weise eingeben.</span><span class="sxs-lookup"><span data-stu-id="4b666-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="4b666-109">Ein Beispiel für einen solchen Thread wäre ein Prozess interner Thread, der Legacy-Skript-debuggger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4b666-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b666-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4b666-110">Requirements</span></span>  
 <span data-ttu-id="4b666-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b666-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b666-112">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="4b666-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b666-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4b666-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b666-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b666-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b666-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b666-115">See also</span></span>

- [<span data-ttu-id="4b666-116">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b666-116">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
