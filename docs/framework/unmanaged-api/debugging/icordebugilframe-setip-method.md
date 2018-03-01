---
title: ICorDebugILFrame::SetIP-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: daffbbd9e961f4fdc7ff2e3c9be57e41e8fa3f78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="d8e79-102">ICorDebugILFrame::SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="d8e79-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="d8e79-103">Legt den Anweisungszeiger auf die angegebene Offsetposition im Microsoft intermediate Language (MSIL)-Code fest.</span><span class="sxs-lookup"><span data-stu-id="d8e79-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8e79-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8e79-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8e79-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8e79-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="d8e79-106">Die Offsetposition im MSIL-Code.</span><span class="sxs-lookup"><span data-stu-id="d8e79-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8e79-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8e79-107">Remarks</span></span>  
 <span data-ttu-id="d8e79-108">Aufrufe von `SetIP` sofort ungültig werden alle Frames und Ketten für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="d8e79-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="d8e79-109">Wenn der Debugger die Frame-Informationen nach einem Aufruf von benötigt `SetIP`, müssen sie eine neue stapelüberwachung ausführen.</span><span class="sxs-lookup"><span data-stu-id="d8e79-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="d8e79-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) versucht, den Stapelrahmen in einem gültigen Zustand zu behalten.</span><span class="sxs-lookup"><span data-stu-id="d8e79-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="d8e79-111">Allerdings auch, wenn der Frame in einem gültigen Zustand ist, weiterhin möglicherweise Probleme, z. B. nicht initialisierten lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="d8e79-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="d8e79-112">Der Aufrufer ist verantwortlich für die Kohärenz des ausgeführten Programms.</span><span class="sxs-lookup"><span data-stu-id="d8e79-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="d8e79-113">Auf 64-Bit-Plattformen kann nicht aus der Anweisungszeiger verschoben werden eine `catch` oder `finally` Block.</span><span class="sxs-lookup"><span data-stu-id="d8e79-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="d8e79-114">Wenn `SetIP` wird aufgerufen, um eine solche Verschiebung auf einer 64-Bit-Plattform zu gestalten, wird einen HRESULT-Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d8e79-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8e79-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d8e79-115">Requirements</span></span>  
 <span data-ttu-id="d8e79-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8e79-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8e79-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8e79-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8e79-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8e79-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8e79-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8e79-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
