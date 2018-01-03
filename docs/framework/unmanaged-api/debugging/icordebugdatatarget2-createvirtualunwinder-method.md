---
title: ICorDebugDataTarget2::CreateVirtualUnwinder-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bffbf95fc38cba6f311e0641b35e2696bd34099
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="805ae-102">ICorDebugDataTarget2::CreateVirtualUnwinder-Methode</span><span class="sxs-lookup"><span data-stu-id="805ae-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="805ae-103">Erstellt einen neuen Stapelentlader, der mit dem Entladen bei einem Anfangskontext beginnt (welcher nicht unbedingt das Blatt eines Threads ist).</span><span class="sxs-lookup"><span data-stu-id="805ae-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="805ae-104">Syntax</span></span>  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
#### <a name="parameters"></a><span data-ttu-id="805ae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="805ae-105">Parameters</span></span>  
 <span data-ttu-id="805ae-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="805ae-106">nativeThreadID</span></span>  
 <span data-ttu-id="805ae-107">[in] Die systemeigene Thread-ID für den Thread, dessen Stapel entladen wird.</span><span class="sxs-lookup"><span data-stu-id="805ae-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="805ae-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="805ae-108">contextFlags</span></span>  
 <span data-ttu-id="805ae-109">[in] Flags, die angeben, welche Teile des Kontexts in `initialContext` definiert sind.</span><span class="sxs-lookup"><span data-stu-id="805ae-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="805ae-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="805ae-110">cbContext</span></span>  
 <span data-ttu-id="805ae-111">[in] Die Größe des `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="805ae-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="805ae-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="805ae-112">initialContext</span></span>  
 <span data-ttu-id="805ae-113">[in] Die Daten im Kontext.</span><span class="sxs-lookup"><span data-stu-id="805ae-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="805ae-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="805ae-114">ppUnwinder</span></span>  
 <span data-ttu-id="805ae-115">[out] Ein Zeiger auf die Adresse eines ICorDebugVirtualUnwinder-Oberflächenobjekts.</span><span class="sxs-lookup"><span data-stu-id="805ae-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="805ae-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="805ae-116">Return Value</span></span>  
 <span data-ttu-id="805ae-117">Bei Erfolg `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="805ae-117">`S_OK` if successful.</span></span> <span data-ttu-id="805ae-118">Alle anderen `HRESULT` weisen auf Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="805ae-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="805ae-119">Alle fehlerhaften `HRESULT` von Mscordbi empfangenen als schwerwiegend und führt dazu, dass [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Methoden zurückzugebenden `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="805ae-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="805ae-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="805ae-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="805ae-121">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="805ae-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="805ae-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="805ae-122">Requirements</span></span>  
 <span data-ttu-id="805ae-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="805ae-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="805ae-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="805ae-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="805ae-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="805ae-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="805ae-126">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="805ae-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="805ae-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="805ae-127">See Also</span></span>  
 [<span data-ttu-id="805ae-128">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="805ae-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="805ae-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="805ae-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
