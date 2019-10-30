---
title: ICorDebugDataTarget2::CreateVirtualUnwinder-Methode
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: f9a9038bd0d268e09d8518fa50534a9959b456de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122187"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="7ddbf-102">ICorDebugDataTarget2::CreateVirtualUnwinder-Methode</span><span class="sxs-lookup"><span data-stu-id="7ddbf-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="7ddbf-103">Erstellt einen neuen Stapelentlader, der mit dem Entladen bei einem Anfangskontext beginnt (welcher nicht unbedingt das Blatt eines Threads ist).</span><span class="sxs-lookup"><span data-stu-id="7ddbf-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ddbf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ddbf-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ddbf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ddbf-105">Parameters</span></span>  
 <span data-ttu-id="7ddbf-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="7ddbf-106">nativeThreadID</span></span>  
 <span data-ttu-id="7ddbf-107">[in] Die systemeigene Thread-ID für den Thread, dessen Stapel entladen wird.</span><span class="sxs-lookup"><span data-stu-id="7ddbf-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="7ddbf-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="7ddbf-108">contextFlags</span></span>  
 <span data-ttu-id="7ddbf-109">[in] Flags, die angeben, welche Teile des Kontexts in `initialContext` definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7ddbf-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="7ddbf-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="7ddbf-110">cbContext</span></span>  
 <span data-ttu-id="7ddbf-111">[in] Die Größe des `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="7ddbf-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="7ddbf-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="7ddbf-112">initialContext</span></span>  
 <span data-ttu-id="7ddbf-113">[in] Die Daten im Kontext.</span><span class="sxs-lookup"><span data-stu-id="7ddbf-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="7ddbf-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="7ddbf-114">ppUnwinder</span></span>  
 <span data-ttu-id="7ddbf-115">[out] Ein Zeiger auf die Adresse eines ICorDebugVirtualUnwinder-Oberflächenobjekts.</span><span class="sxs-lookup"><span data-stu-id="7ddbf-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ddbf-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7ddbf-116">Return Value</span></span>  
 <span data-ttu-id="7ddbf-117">Bei Erfolg `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="7ddbf-117">`S_OK` if successful.</span></span> <span data-ttu-id="7ddbf-118">Alle anderen `HRESULT` weisen auf Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="7ddbf-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="7ddbf-119">Alle von "mscordbi empfangenen fehlerhaften `HRESULT` werden als schwerwiegend angesehen und bewirken, dass [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Methoden `CORDBG_E_DATA_TARGET_ERROR`zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7ddbf-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ddbf-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ddbf-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ddbf-121">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7ddbf-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ddbf-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ddbf-122">Requirements</span></span>  
 <span data-ttu-id="7ddbf-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ddbf-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ddbf-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ddbf-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ddbf-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ddbf-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ddbf-126">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ddbf-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ddbf-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ddbf-127">See also</span></span>

- [<span data-ttu-id="7ddbf-128">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ddbf-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="7ddbf-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7ddbf-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
