---
title: ICorDebugNativeFrame::SetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
ms.openlocfilehash: 1d978cab0817af68356d95d635f8d2bfa3fd546a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096740"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="0ddd0-102">ICorDebugNativeFrame::SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="0ddd0-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="0ddd0-103">Legt den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code fest.</span><span class="sxs-lookup"><span data-stu-id="0ddd0-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ddd0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ddd0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ddd0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ddd0-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="0ddd0-106">in Die Offset Position im systemeigenen Code.</span><span class="sxs-lookup"><span data-stu-id="0ddd0-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ddd0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ddd0-107">Remarks</span></span>  
 <span data-ttu-id="0ddd0-108">Durch Aufrufe von `SetIP` werden alle Frames und Ketten für den aktuellen Thread sofort ungültig.</span><span class="sxs-lookup"><span data-stu-id="0ddd0-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="0ddd0-109">Wenn der Debugger nach einem Aufruf`SetIP`Frame Informationen benötigt, muss er eine neue Stapel Überwachung ausführen.</span><span class="sxs-lookup"><span data-stu-id="0ddd0-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="0ddd0-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) versucht, den Stapel Rahmen in einem gültigen Zustand zu belassen.</span><span class="sxs-lookup"><span data-stu-id="0ddd0-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="0ddd0-111">Auch wenn sich der Frame in einem gültigen Zustand befindet, soweit die Laufzeit betroffen ist, können Probleme wie nicht initialisierte lokale Variablen usw. auftreten.</span><span class="sxs-lookup"><span data-stu-id="0ddd0-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="0ddd0-112">Der Aufrufer ist dafür verantwortlich, die Kohärenz des laufenden Programms zu sichern.</span><span class="sxs-lookup"><span data-stu-id="0ddd0-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="0ddd0-113">Auf 64-Bit-Plattformen kann der Anweisungs Zeiger nicht aus einem `catch` oder `finally` Block verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="0ddd0-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="0ddd0-114">Wenn `SetIP` aufgerufen wird, um eine solche Verschiebung auf einer 64-Bit-Plattform vorzunehmen, wird ein HRESULT zurückgegeben, das einen Fehler anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0ddd0-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ddd0-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ddd0-115">Requirements</span></span>  
 <span data-ttu-id="0ddd0-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ddd0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ddd0-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ddd0-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ddd0-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ddd0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ddd0-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ddd0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddd0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ddd0-120">See also</span></span>
