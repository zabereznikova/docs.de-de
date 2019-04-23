---
title: ICorDebugDataTarget2::CreateVirtualUnwinder-Methode
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c8befed8bc810344b2a3344212a6a4a854300e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164657"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="b8ac7-102">ICorDebugDataTarget2::CreateVirtualUnwinder-Methode</span><span class="sxs-lookup"><span data-stu-id="b8ac7-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="b8ac7-103">Erstellt einen neuen Stapelentlader, der mit dem Entladen bei einem Anfangskontext beginnt (welcher nicht unbedingt das Blatt eines Threads ist).</span><span class="sxs-lookup"><span data-stu-id="b8ac7-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8ac7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8ac7-104">Syntax</span></span>  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8ac7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8ac7-105">Parameters</span></span>  
 <span data-ttu-id="b8ac7-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="b8ac7-106">nativeThreadID</span></span>  
 <span data-ttu-id="b8ac7-107">[in] Die systemeigene Thread-ID für den Thread, dessen Stapel entladen wird.</span><span class="sxs-lookup"><span data-stu-id="b8ac7-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="b8ac7-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="b8ac7-108">contextFlags</span></span>  
 <span data-ttu-id="b8ac7-109">[in] Flags, die angeben, welche Teile des Kontexts in `initialContext` definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b8ac7-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="b8ac7-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="b8ac7-110">cbContext</span></span>  
 <span data-ttu-id="b8ac7-111">[in] Die Größe des `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="b8ac7-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="b8ac7-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="b8ac7-112">initialContext</span></span>  
 <span data-ttu-id="b8ac7-113">[in] Die Daten im Kontext.</span><span class="sxs-lookup"><span data-stu-id="b8ac7-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="b8ac7-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="b8ac7-114">ppUnwinder</span></span>  
 <span data-ttu-id="b8ac7-115">[out] Ein Zeiger auf die Adresse eines ICorDebugVirtualUnwinder-Oberflächenobjekts.</span><span class="sxs-lookup"><span data-stu-id="b8ac7-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8ac7-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b8ac7-116">Return Value</span></span>  
 <span data-ttu-id="b8ac7-117">Bei Erfolg `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="b8ac7-117">`S_OK` if successful.</span></span> <span data-ttu-id="b8ac7-118">Alle anderen `HRESULT` weisen auf Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="b8ac7-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="b8ac7-119">Alle fehlerhaften `HRESULT` von Mscordbi empfangenen als schwerwiegend und führt dazu, dass [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Methoden zurückgeben `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="b8ac7-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8ac7-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8ac7-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8ac7-121">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b8ac7-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8ac7-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8ac7-122">Requirements</span></span>  
 <span data-ttu-id="b8ac7-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8ac7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8ac7-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8ac7-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8ac7-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8ac7-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8ac7-126">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8ac7-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ac7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8ac7-127">See also</span></span>

- [<span data-ttu-id="b8ac7-128">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8ac7-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="b8ac7-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b8ac7-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
