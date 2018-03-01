---
title: ICorDebugProcess2::ClearUnmanagedBreakpoint-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 14258ef1ae473fc867d86c89ec877ddbf8c80213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="23897-102">ICorDebugProcess2::ClearUnmanagedBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="23897-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="23897-103">Entfernt einen zuvor festgelegten Haltepunkt an der angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="23897-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23897-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23897-104">Syntax</span></span>  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23897-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23897-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="23897-106">[in] Ein `CORDB_ADDRESS` Wert, der die Adresse angibt, an dem der Haltepunkt festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="23897-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23897-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23897-107">Remarks</span></span>  
 <span data-ttu-id="23897-108">Die angegebene Breakpoint würde zuvor festgelegten durch einen früheren Aufruf [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="23897-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="23897-109">Die `ClearUnmanagedBreakpoint` Methode kann aufgerufen werden, während der zu debuggende Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="23897-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="23897-110">Die `ClearUnmanagedBreakpoint` Methode gibt einen Fehlercode zurück, wenn der Debugger im ausschließlich verwalteten Modus verbunden ist oder wenn kein Haltepunkt an der angegebenen Adresse vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="23897-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23897-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23897-111">Requirements</span></span>  
 <span data-ttu-id="23897-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23897-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23897-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23897-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23897-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23897-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23897-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23897-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
