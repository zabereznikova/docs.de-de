---
title: ICorDebugDataTarget2::CreateVirtualUnwinder-Methode
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 0967b1cda86eab35015279edeed9a6b9852036b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713937"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="2ca3f-102">ICorDebugDataTarget2::CreateVirtualUnwinder-Methode</span><span class="sxs-lookup"><span data-stu-id="2ca3f-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>

<span data-ttu-id="2ca3f-103">Erstellt einen neuen Stapelentlader, der mit dem Entladen bei einem Anfangskontext beginnt (welcher nicht unbedingt das Blatt eines Threads ist).</span><span class="sxs-lookup"><span data-stu-id="2ca3f-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca3f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ca3f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ca3f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ca3f-105">Parameters</span></span>  

 <span data-ttu-id="2ca3f-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="2ca3f-106">nativeThreadID</span></span>  
 <span data-ttu-id="2ca3f-107">[in] Die systemeigene Thread-ID für den Thread, dessen Stapel entladen wird.</span><span class="sxs-lookup"><span data-stu-id="2ca3f-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="2ca3f-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="2ca3f-108">contextFlags</span></span>  
 <span data-ttu-id="2ca3f-109">[in] Flags, die angeben, welche Teile des Kontexts in `initialContext` definiert sind.</span><span class="sxs-lookup"><span data-stu-id="2ca3f-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="2ca3f-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="2ca3f-110">cbContext</span></span>  
 <span data-ttu-id="2ca3f-111">[in] Die Größe des `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="2ca3f-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="2ca3f-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="2ca3f-112">initialContext</span></span>  
 <span data-ttu-id="2ca3f-113">[in] Die Daten im Kontext.</span><span class="sxs-lookup"><span data-stu-id="2ca3f-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="2ca3f-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="2ca3f-114">ppUnwinder</span></span>  
 <span data-ttu-id="2ca3f-115">[out] Ein Zeiger auf die Adresse eines ICorDebugVirtualUnwinder-Oberflächenobjekts.</span><span class="sxs-lookup"><span data-stu-id="2ca3f-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ca3f-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2ca3f-116">Return Value</span></span>  

 <span data-ttu-id="2ca3f-117">Bei Erfolg `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="2ca3f-117">`S_OK` if successful.</span></span> <span data-ttu-id="2ca3f-118">Alle anderen `HRESULT` weisen auf Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="2ca3f-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="2ca3f-119">Alle `HRESULT` von "mscordbi empfangenen Fehler werden als schwerwiegend angesehen und bewirken, dass [ICorDebug](icordebug-interface.md) -Methoden zurückgegeben werden `CORDBG_E_DATA_TARGET_ERROR` .</span><span class="sxs-lookup"><span data-stu-id="2ca3f-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ca3f-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ca3f-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ca3f-121">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2ca3f-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ca3f-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2ca3f-122">Requirements</span></span>  

 <span data-ttu-id="2ca3f-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ca3f-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ca3f-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ca3f-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ca3f-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ca3f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ca3f-126">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ca3f-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca3f-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ca3f-127">See also</span></span>

- [<span data-ttu-id="2ca3f-128">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ca3f-128">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="2ca3f-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2ca3f-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
