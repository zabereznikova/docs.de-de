---
title: ICorDebugMutableDataTarget::WriteVirtual-Methode
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 6325dba99fba0ab5e2f752a0635fdd428d3065eb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206742"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="df47e-102">ICorDebugMutableDataTarget::WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="df47e-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="df47e-103">Schreibt Speicher in den Prozessadressraum.</span><span class="sxs-lookup"><span data-stu-id="df47e-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df47e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df47e-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df47e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df47e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="df47e-106">[in] Die Adresse, an die der Inhalt von `pBuffer` geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="df47e-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="df47e-107">[in] Ein Zeiger auf ein Bytearray, das die zu schreibenden Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="df47e-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="df47e-108">[in] Die Anzahl von Bytes in `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="df47e-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df47e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="df47e-109">Return Value</span></span>  
 <span data-ttu-id="df47e-110">`S_OK` bei erfolgreichem Verlauf oder ein anderes `HRESULT` im Fall eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="df47e-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df47e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df47e-111">Remarks</span></span>  
 <span data-ttu-id="df47e-112">Wenn Bytes nicht geschrieben werden können, tritt ein Fehler beim Methodenaufruf auf, und es werden keine Bytes im Zieladressraum geändert.</span><span class="sxs-lookup"><span data-stu-id="df47e-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="df47e-113">(Andernfalls würde sich das Ziel in einem inkonsistenten Zustand befinden, wodurch ein weiteres Debuggen unzuverlässig wäre.)</span><span class="sxs-lookup"><span data-stu-id="df47e-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df47e-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="df47e-114">Requirements</span></span>  
 <span data-ttu-id="df47e-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df47e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df47e-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df47e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df47e-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df47e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df47e-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df47e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df47e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df47e-119">See also</span></span>

- [<span data-ttu-id="df47e-120">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df47e-120">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="df47e-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="df47e-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
