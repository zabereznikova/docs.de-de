---
title: ICorDebugProcess2::ClearUnmanagedBreakpoint-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
ms.openlocfilehash: 8377ead42c752d8ebe9813d9e00662b94339f8a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137245"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="6affc-102">ICorDebugProcess2::ClearUnmanagedBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="6affc-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="6affc-103">Entfernt einen zuvor festgelegten Haltepunkt an der angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="6affc-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6affc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6affc-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6affc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6affc-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="6affc-106">in Ein `CORDB_ADDRESS` Wert, der die Adresse angibt, an der der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="6affc-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6affc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6affc-107">Remarks</span></span>  
 <span data-ttu-id="6affc-108">Der angegebene Haltepunkt hätte zuvor durch einen früheren [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)-Befehl festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6affc-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="6affc-109">Die `ClearUnmanagedBreakpoint`-Methode kann aufgerufen werden, während der Prozess, der debuggt wird, ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6affc-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="6affc-110">Die `ClearUnmanagedBreakpoint`-Methode gibt einen Fehlercode zurück, wenn der Debugger im verwalteten Modus angefügt wird oder wenn an der angegebenen Adresse kein Haltepunkt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6affc-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6affc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6affc-111">Requirements</span></span>  
 <span data-ttu-id="6affc-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6affc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6affc-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6affc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6affc-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6affc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6affc-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6affc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
