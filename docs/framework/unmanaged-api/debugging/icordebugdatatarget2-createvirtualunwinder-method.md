---
title: ICorDebugDataTarget2::CreateVirtualUnwinder-Methode
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 9fc4facda6253d0c68dcf89b2a1b06e639734efe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788854"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="22369-102">ICorDebugDataTarget2::CreateVirtualUnwinder-Methode</span><span class="sxs-lookup"><span data-stu-id="22369-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="22369-103">Erstellt einen neuen Stapelentlader, der mit dem Entladen bei einem Anfangskontext beginnt (welcher nicht unbedingt das Blatt eines Threads ist).</span><span class="sxs-lookup"><span data-stu-id="22369-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22369-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22369-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="22369-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="22369-105">Parameters</span></span>  
 <span data-ttu-id="22369-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="22369-106">nativeThreadID</span></span>  
 <span data-ttu-id="22369-107">[in] Die systemeigene Thread-ID für den Thread, dessen Stapel entladen wird.</span><span class="sxs-lookup"><span data-stu-id="22369-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="22369-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="22369-108">contextFlags</span></span>  
 <span data-ttu-id="22369-109">[in] Flags, die angeben, welche Teile des Kontexts in `initialContext` definiert sind.</span><span class="sxs-lookup"><span data-stu-id="22369-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="22369-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="22369-110">cbContext</span></span>  
 <span data-ttu-id="22369-111">[in] Die Größe des `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="22369-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="22369-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="22369-112">initialContext</span></span>  
 <span data-ttu-id="22369-113">[in] Die Daten im Kontext.</span><span class="sxs-lookup"><span data-stu-id="22369-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="22369-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="22369-114">ppUnwinder</span></span>  
 <span data-ttu-id="22369-115">[out] Ein Zeiger auf die Adresse eines ICorDebugVirtualUnwinder-Oberflächenobjekts.</span><span class="sxs-lookup"><span data-stu-id="22369-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22369-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="22369-116">Return Value</span></span>  
 <span data-ttu-id="22369-117">Bei Erfolg `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="22369-117">`S_OK` if successful.</span></span> <span data-ttu-id="22369-118">Alle anderen `HRESULT` weisen auf Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="22369-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="22369-119">Alle von "mscordbi empfangenen fehlerhaften `HRESULT` werden als schwerwiegend angesehen und bewirken, dass [ICorDebug](icordebug-interface.md) -Methoden `CORDBG_E_DATA_TARGET_ERROR`zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="22369-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22369-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22369-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22369-121">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="22369-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22369-122">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22369-122">Requirements</span></span>  
 <span data-ttu-id="22369-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22369-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22369-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22369-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22369-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22369-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22369-126">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22369-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22369-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22369-127">See also</span></span>

- [<span data-ttu-id="22369-128">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22369-128">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="22369-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="22369-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
