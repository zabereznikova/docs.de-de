---
title: 'Icordebugmutabledatatarget:: Write Virtual-Methode'
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 5947caa8dfb97574bb4b3c5634d962df153211c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132677"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="c8d4d-102">Icordebugmutabledatatarget:: Write Virtual-Methode</span><span class="sxs-lookup"><span data-stu-id="c8d4d-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="c8d4d-103">Schreibt Speicher in den Prozessadressraum.</span><span class="sxs-lookup"><span data-stu-id="c8d4d-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8d4d-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8d4d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8d4d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c8d4d-106">[in] Die Adresse, an die der Inhalt von `pBuffer` geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="c8d4d-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="c8d4d-107">[in] Ein Zeiger auf ein Bytearray, das die zu schreibenden Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="c8d4d-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="c8d4d-108">[in] Die Anzahl von Bytes in `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="c8d4d-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8d4d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c8d4d-109">Return Value</span></span>  
 <span data-ttu-id="c8d4d-110">`S_OK` bei erfolgreichem Verlauf oder ein anderes `HRESULT` im Fall eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="c8d4d-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8d4d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8d4d-111">Remarks</span></span>  
 <span data-ttu-id="c8d4d-112">Wenn Bytes nicht geschrieben werden können, tritt ein Fehler beim Methodenaufruf auf, und es werden keine Bytes im Zieladressraum geändert.</span><span class="sxs-lookup"><span data-stu-id="c8d4d-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="c8d4d-113">(Andernfalls würde sich das Ziel in einem inkonsistenten Zustand befinden, wodurch ein weiteres Debuggen unzuverlässig wäre.)</span><span class="sxs-lookup"><span data-stu-id="c8d4d-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8d4d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8d4d-114">Requirements</span></span>  
 <span data-ttu-id="c8d4d-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8d4d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8d4d-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8d4d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8d4d-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8d4d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8d4d-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8d4d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d4d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8d4d-119">See also</span></span>

- [<span data-ttu-id="c8d4d-120">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8d4d-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="c8d4d-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c8d4d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
