---
title: ICorDebugILFrame2::RemapFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92885d2a6514839a864d6a345dd8af8b07b90c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946522"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="195cf-102">ICorDebugILFrame2::RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="195cf-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="195cf-103">Ordnet eine bearbeitete Funktion durch Angabe des neuen Microsoft intermediate Language (MSIL)-Offsets neu</span><span class="sxs-lookup"><span data-stu-id="195cf-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="195cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="195cf-104">Syntax</span></span>  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="195cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="195cf-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="195cf-106">[in] Der Stapelrahmen neue MSIL-Offset zu dem der Anweisungszeiger eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="195cf-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="195cf-107">Dieser Wert muss es sich um ein Sequenzpunkt sein.</span><span class="sxs-lookup"><span data-stu-id="195cf-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="195cf-108">Es ist der Verantwortung des Aufrufers um sicherzustellen, dass die Gültigkeit dieses Werts.</span><span class="sxs-lookup"><span data-stu-id="195cf-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="195cf-109">Der MSIL-Offset ist z. B. nicht gültig, wenn sie außerhalb der Grenzen der Funktion.</span><span class="sxs-lookup"><span data-stu-id="195cf-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="195cf-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="195cf-110">Remarks</span></span>  
 <span data-ttu-id="195cf-111">Wenn die Funktion eines Frames bearbeitet wurde, kann der Debugger Aufrufen der `RemapFunction` Methode in der neuesten Version der Funktion des Frames austauschen, damit sie ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="195cf-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="195cf-112">Die Ausführung des Codes beginnt an der angegebenen MSIL-Offset.</span><span class="sxs-lookup"><span data-stu-id="195cf-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="195cf-113">Aufrufen von `RemapFunction`, z. B. Aufrufen von [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), alle debugging-Schnittstellen, die im Zusammenhang mit der eine stapelüberwachung für den Thread zu generieren, wird sofort ungültig.</span><span class="sxs-lookup"><span data-stu-id="195cf-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="195cf-114">Diese Schnittstellen umfassen [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame und ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="195cf-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="195cf-115">Die `RemapFunction` Methode kann aufgerufen werden, nur im Kontext des aktuellen Frames und nur in einem der folgenden Fälle:</span><span class="sxs-lookup"><span data-stu-id="195cf-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="195cf-116">Nach dem Empfang einer [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) Rückruf, der noch nicht fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="195cf-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="195cf-117">Während der Ausführung von Code beendet wird, da ein [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) Ereignis für diesen Frame.</span><span class="sxs-lookup"><span data-stu-id="195cf-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="195cf-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="195cf-118">Requirements</span></span>  
 <span data-ttu-id="195cf-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="195cf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="195cf-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="195cf-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="195cf-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="195cf-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="195cf-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="195cf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
