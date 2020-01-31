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
ms.openlocfilehash: f4f73b99b4cb48690a2a8611dbf5a5420adab5d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794356"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="ab1bf-102">ICorDebugILFrame2::RemapFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="ab1bf-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="ab1bf-103">Ordnet eine bearbeitete Funktion neu zu, indem der neue MSIL-Offset (Microsoft Intermediate Language) angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab1bf-104">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab1bf-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ab1bf-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="ab1bf-106">in Der neue MSIL-Offset des Stapel Rahmens, bei dem der Anweisungs Zeiger platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="ab1bf-107">Dieser Wert muss ein Sequenz Punkt sein.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="ab1bf-108">Es liegt in der Verantwortung des Aufrufers, die Gültigkeit dieses Werts sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="ab1bf-109">Beispielsweise ist der MSIL-Offset nicht gültig, wenn er sich außerhalb der Grenzen der Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab1bf-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab1bf-110">Remarks</span></span>  
 <span data-ttu-id="ab1bf-111">Wenn die Funktion eines Frames bearbeitet wurde, kann der Debugger die `RemapFunction`-Methode zum austauschen in der aktuellen Version der Funktion des Frames abrufen, sodass Sie ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="ab1bf-112">Die Codeausführung beginnt am angegebenen MSIL-Offset.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab1bf-113">Wenn Sie `RemapFunction`aufrufen, wie z. b. [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md), werden alle Debugschnittstellen, die mit dem Erstellen einer Stapel Überwachung für den Thread verknüpft sind, sofort ungültig.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="ab1bf-114">Zu diesen Schnittstellen gehören [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame und ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-114">These interfaces include [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="ab1bf-115">Die `RemapFunction`-Methode kann nur im Kontext des aktuellen Frames aufgerufen werden, und zwar nur in einem der folgenden Fälle:</span><span class="sxs-lookup"><span data-stu-id="ab1bf-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="ab1bf-116">Nach dem Empfang eines [ICorDebugManagedCallback2:: FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) -Rückrufs, der noch nicht fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="ab1bf-117">Während die Codeausführung aufgrund eines [ICorDebugManagedCallback:: EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) -Ereignisses für diesen Frame beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ab1bf-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab1bf-118">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab1bf-118">Requirements</span></span>  
 <span data-ttu-id="ab1bf-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab1bf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab1bf-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab1bf-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab1bf-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab1bf-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab1bf-122">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab1bf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
