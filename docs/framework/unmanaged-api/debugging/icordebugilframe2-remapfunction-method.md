---
title: ICorDebugILFrame2::RemapFunction-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2.RemapFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9fed4759576d1b6d2fec1a5e9c1e36019e5944c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="ac442-102">ICorDebugILFrame2::RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="ac442-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="ac442-103">Ordnet eine bearbeitete Funktion durch Angabe des neuen Microsoft intermediate Language (MSIL)-Offsets</span><span class="sxs-lookup"><span data-stu-id="ac442-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac442-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac442-104">Syntax</span></span>  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac442-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac442-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="ac442-106">[in] Der Stapelrahmen neue MSIL-Offset an dem der Anweisungszeiger platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac442-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="ac442-107">Dieser Wert muss ein Sequenzpunkt sein.</span><span class="sxs-lookup"><span data-stu-id="ac442-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="ac442-108">Es ist die Verantwortung des Aufrufers, um die Gültigkeit dieses Werts sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ac442-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="ac442-109">Der MSIL-Offset ist beispielsweise ungültig, wenn es außerhalb des gültigen Bereichs der Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="ac442-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac442-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac442-110">Remarks</span></span>  
 <span data-ttu-id="ac442-111">Wenn die Funktion eines Frames bearbeitet wurde, kann der Debugger Aufrufen der `RemapFunction` Methode, um in der neuesten Version der Funktion des Frames austauschen, damit sie ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac442-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="ac442-112">Die Ausführung des Codes beginnt an der angegebenen MSIL-Offset.</span><span class="sxs-lookup"><span data-stu-id="ac442-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac442-113">Aufrufen von `RemapFunction`, z. B. Aufrufen [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), werden sofort alle debugging-Schnittstellen, die im Zusammenhang mit der eine stapelüberwachung für den Thread generiert ungültig.</span><span class="sxs-lookup"><span data-stu-id="ac442-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="ac442-114">Zu diesen Schnittstellen gehören [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame und ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="ac442-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="ac442-115">Die `RemapFunction` Methode kann aufgerufen werden, nur im Kontext des aktuellen Frames und nur in einem der folgenden Fälle:</span><span class="sxs-lookup"><span data-stu-id="ac442-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
-   <span data-ttu-id="ac442-116">Nach dem Empfang einer [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) Rückruf, der noch nicht fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="ac442-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
-   <span data-ttu-id="ac442-117">Während der Ausführung von Code aufgrund des beendet wird ein [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) -Ereignis für dieses Rahmens.</span><span class="sxs-lookup"><span data-stu-id="ac442-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac442-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac442-118">Requirements</span></span>  
 <span data-ttu-id="ac442-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac442-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac442-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac442-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac442-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac442-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac442-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac442-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
