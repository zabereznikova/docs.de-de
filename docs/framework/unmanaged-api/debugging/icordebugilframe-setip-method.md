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
ms.openlocfilehash: fdc3d96fd5ad9a6ff59b863cd3f0450283ea0146
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721373"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="e4afc-102">ICorDebugILFrame::SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="e4afc-102">ICorDebugILFrame::SetIP Method</span></span>

<span data-ttu-id="e4afc-103">Legt den Anweisungs Zeiger auf die angegebene Offset Position im MSIL-Code (Microsoft Intermediate Language) fest.</span><span class="sxs-lookup"><span data-stu-id="e4afc-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4afc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4afc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4afc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4afc-105">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="e4afc-106">Die Offset Position im MSIL-Code.</span><span class="sxs-lookup"><span data-stu-id="e4afc-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4afc-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4afc-107">Remarks</span></span>  

 <span data-ttu-id="e4afc-108">Ruft auf, um `SetIP` alle Frames und Ketten für den aktuellen Thread sofort für ungültig zu erklären.</span><span class="sxs-lookup"><span data-stu-id="e4afc-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="e4afc-109">Wenn der Debugger nach einem-Aufrufvorgang Frame Informationen benötigt `SetIP` , muss er eine neue Stapel Überwachung ausführen.</span><span class="sxs-lookup"><span data-stu-id="e4afc-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="e4afc-110">[ICorDebug](icordebug-interface.md) versucht, den Stapel Rahmen in einem gültigen Zustand zu belassen.</span><span class="sxs-lookup"><span data-stu-id="e4afc-110">[ICorDebug](icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="e4afc-111">Auch wenn sich der Frame in einem gültigen Zustand befindet, sind möglicherweise weiterhin Probleme aufgetreten, z. b. nicht initialisierte lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="e4afc-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="e4afc-112">Der Aufrufer ist dafür verantwortlich, die Kohärenz des laufenden Programms sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="e4afc-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="e4afc-113">Auf 64-Bit-Plattformen kann der Anweisungs Zeiger nicht aus einem-oder-Block verschoben werden `catch` `finally` .</span><span class="sxs-lookup"><span data-stu-id="e4afc-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="e4afc-114">Wenn `SetIP` aufgerufen wird, um eine solche Verschiebung auf einer 64-Bit-Plattform vorzunehmen, wird ein HRESULT zurückgegeben, das einen Fehler anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e4afc-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4afc-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e4afc-115">Requirements</span></span>  

 <span data-ttu-id="e4afc-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4afc-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4afc-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4afc-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4afc-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4afc-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4afc-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4afc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
