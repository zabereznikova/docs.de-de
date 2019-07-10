---
title: ICorDebugILFrame::SetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2af3f58fa7714b3c2b0ba387b1da650f0638dd6c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758778"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="ea74a-102">ICorDebugILFrame::SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="ea74a-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="ea74a-103">Legt den Anweisungszeiger am angegebenen Offset Speicherort im Microsoft intermediate Language (MSIL)-Code fest.</span><span class="sxs-lookup"><span data-stu-id="ea74a-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea74a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea74a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea74a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea74a-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="ea74a-106">Die Offsetposition im MSIL-Code.</span><span class="sxs-lookup"><span data-stu-id="ea74a-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea74a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea74a-107">Remarks</span></span>  
 <span data-ttu-id="ea74a-108">Aufrufe von `SetIP` direkt für ungültig erklären alle Rahmen und Ketten für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="ea74a-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="ea74a-109">Wenn der Debugger die Frame-Informationen nach einem Aufruf von benötigt `SetIP`, müssen sie eine neue stapelüberwachung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ea74a-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="ea74a-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) wird versucht, den Stapelrahmen in einem gültigen Zustand zu halten.</span><span class="sxs-lookup"><span data-stu-id="ea74a-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="ea74a-111">Allerdings auch, wenn der Frame in einem gültigen Zustand ist, gibt es immer noch möglicherweise Probleme wie z. B. nicht initialisierten lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="ea74a-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="ea74a-112">Der Aufrufer ist verantwortlich für die Kohärenz des laufenden Programms.</span><span class="sxs-lookup"><span data-stu-id="ea74a-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="ea74a-113">Auf 64-Bit-Plattformen kann nicht von der Anweisungszeiger verschoben werden eine `catch` oder `finally` Block.</span><span class="sxs-lookup"><span data-stu-id="ea74a-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="ea74a-114">Wenn `SetIP` wird aufgerufen, um eine solche Verschiebung auf einer 64-Bit-Plattform zu machen, wird einen HRESULT-Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ea74a-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea74a-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea74a-115">Requirements</span></span>  
 <span data-ttu-id="ea74a-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea74a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea74a-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea74a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea74a-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea74a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea74a-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea74a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
