---
title: ICorDebugVirtualUnwinder::GetContext-Methode
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec68e36e2e5a06836d0f5d5758a230591626b03e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744101"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a><span data-ttu-id="319e2-102">ICorDebugVirtualUnwinder::GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="319e2-102">ICorDebugVirtualUnwinder::GetContext Method</span></span>
<span data-ttu-id="319e2-103">Ruft den aktuellen Kontext dieses Entladers ab.</span><span class="sxs-lookup"><span data-stu-id="319e2-103">Gets the current context of this unwinder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="319e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="319e2-104">Syntax</span></span>  
  
```  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="319e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="319e2-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="319e2-106">[in] Flags, die angeben, welche Teile des Kontexts zurückgegeben werden (in "WinNT.h" definiert).</span><span class="sxs-lookup"><span data-stu-id="319e2-106">[in] Flags that specify which parts of the context to return (defined in WinNT.h).</span></span>  
  
 `cbContextBuf`  
 <span data-ttu-id="319e2-107">[in] Die Anzahl von Bytes in `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="319e2-107">[in] The number of bytes in `contextBuf`.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="319e2-108">[out] Ein Zeiger auf die Anzahl der tatsächlich in `contextBuf` geschriebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="319e2-108">[out] A pointer to the number of bytes actually written to `contextBuf`.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="319e2-109">[out] Ein Bytearray, das den aktuellen Kontext dieses Entladers enthält.</span><span class="sxs-lookup"><span data-stu-id="319e2-109">[out] A byte array that contains the current context of this unwinder.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="319e2-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="319e2-110">Return Value</span></span>  
 <span data-ttu-id="319e2-111">Alle von "mscordbi" empfangenen HRESULT-Fehlerwerte gelten als schwerwiegend und bewirken, dass "ICorDebug"-APIs `CORDBG_E_DATA_TARGET_ERROR` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="319e2-111">Any failing HRESULT value received by mscordbi is considered fatal and will cause ICorDebug APIs to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="319e2-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="319e2-112">Remarks</span></span>  
 <span data-ttu-id="319e2-113">Den anfänglichen Wert festlegen die `contextBuf` Argument auf den Kontextpuffer zurückgegeben, indem die [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="319e2-113">You set the initial value of the `contextBuf` argument to the context buffer returned by calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="319e2-114">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="319e2-114">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="319e2-115">Da beim Entladen möglicherweise nur eine Teilmenge der Register (z. B. nur die nicht permanenten Register) wiederhergestellt werden, stimmt der Kontext möglicherweise nicht genau mit dem Registrierungszustand zum Zeitpunkt des eigentlichen Methodenaufrufs überein.</span><span class="sxs-lookup"><span data-stu-id="319e2-115">Because unwinding may only restore a subset of the registers, such as the non-volatile registers only, the context may not exactly match the register state at the time of the actual method call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="319e2-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="319e2-116">Requirements</span></span>  
 <span data-ttu-id="319e2-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="319e2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="319e2-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="319e2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="319e2-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="319e2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="319e2-120">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="319e2-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="319e2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="319e2-121">See also</span></span>
- [<span data-ttu-id="319e2-122">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="319e2-122">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="319e2-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="319e2-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
