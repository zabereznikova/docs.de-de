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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc34ab9c8dbfe10282f36a241a4e433debef7dd0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420494"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="76545-102">ICorDebugProcess2::ClearUnmanagedBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="76545-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="76545-103">Entfernt einen zuvor festgelegten Haltepunkt an der angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="76545-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76545-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76545-104">Syntax</span></span>  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76545-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="76545-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="76545-106">[in] Ein `CORDB_ADDRESS` Wert, der die Adresse angibt, an dem der Haltepunkt festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="76545-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76545-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="76545-107">Remarks</span></span>  
 <span data-ttu-id="76545-108">Die angegebene Breakpoint würde zuvor festgelegten durch einen früheren Aufruf [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="76545-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="76545-109">Die `ClearUnmanagedBreakpoint` Methode kann aufgerufen werden, während der zu debuggende Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="76545-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="76545-110">Die `ClearUnmanagedBreakpoint` Methode gibt einen Fehlercode zurück, wenn der Debugger im ausschließlich verwalteten Modus verbunden ist oder wenn kein Haltepunkt an der angegebenen Adresse vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="76545-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76545-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="76545-111">Requirements</span></span>  
 <span data-ttu-id="76545-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76545-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76545-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76545-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76545-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76545-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76545-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76545-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
