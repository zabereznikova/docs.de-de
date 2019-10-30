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
ms.openlocfilehash: 60273d7cf91be04c5fc3041260e4bb146ce9a45e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095430"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="4a382-102">ICorDebugILFrame::SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="4a382-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="4a382-103">Legt den Anweisungs Zeiger auf die angegebene Offset Position im MSIL-Code (Microsoft Intermediate Language) fest.</span><span class="sxs-lookup"><span data-stu-id="4a382-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a382-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a382-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a382-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a382-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="4a382-106">Die Offset Position im MSIL-Code.</span><span class="sxs-lookup"><span data-stu-id="4a382-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a382-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a382-107">Remarks</span></span>  
 <span data-ttu-id="4a382-108">Durch Aufrufe von `SetIP` werden alle Frames und Ketten für den aktuellen Thread sofort ungültig.</span><span class="sxs-lookup"><span data-stu-id="4a382-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="4a382-109">Wenn der Debugger nach einem Aufruf`SetIP`Frame Informationen benötigt, muss er eine neue Stapel Überwachung ausführen.</span><span class="sxs-lookup"><span data-stu-id="4a382-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="4a382-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) versucht, den Stapel Rahmen in einem gültigen Zustand zu belassen.</span><span class="sxs-lookup"><span data-stu-id="4a382-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="4a382-111">Auch wenn sich der Frame in einem gültigen Zustand befindet, sind möglicherweise weiterhin Probleme aufgetreten, z. b. nicht initialisierte lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="4a382-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="4a382-112">Der Aufrufer ist dafür verantwortlich, die Kohärenz des laufenden Programms sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="4a382-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="4a382-113">Auf 64-Bit-Plattformen kann der Anweisungs Zeiger nicht aus einem `catch` oder `finally` Block verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="4a382-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="4a382-114">Wenn `SetIP` aufgerufen wird, um eine solche Verschiebung auf einer 64-Bit-Plattform vorzunehmen, wird ein HRESULT zurückgegeben, das einen Fehler anzeigt.</span><span class="sxs-lookup"><span data-stu-id="4a382-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a382-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4a382-115">Requirements</span></span>  
 <span data-ttu-id="4a382-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a382-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a382-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a382-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a382-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a382-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a382-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a382-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
