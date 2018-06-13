---
title: ICorDebugMutableDataTarget::WriteVirtual-Methode
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 184ae290b3a7d86a3c0351d4cfb072bce37337d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417413"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="61a6a-102">ICorDebugMutableDataTarget::WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="61a6a-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="61a6a-103">Schreibt Speicher in den Prozessadressraum.</span><span class="sxs-lookup"><span data-stu-id="61a6a-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61a6a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61a6a-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61a6a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61a6a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="61a6a-106">[in] Die Adresse, an die der Inhalt von `pBuffer` geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="61a6a-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="61a6a-107">[in] Ein Zeiger auf ein Bytearray, das die zu schreibenden Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="61a6a-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="61a6a-108">[in] Die Anzahl von Bytes in `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="61a6a-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61a6a-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="61a6a-109">Return Value</span></span>  
 <span data-ttu-id="61a6a-110">`S_OK` bei erfolgreichem Verlauf oder ein anderes `HRESULT` im Fall eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="61a6a-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61a6a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61a6a-111">Remarks</span></span>  
 <span data-ttu-id="61a6a-112">Wenn Bytes nicht geschrieben werden können, tritt ein Fehler beim Methodenaufruf auf, und es werden keine Bytes im Zieladressraum geändert.</span><span class="sxs-lookup"><span data-stu-id="61a6a-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="61a6a-113">(Andernfalls würde sich das Ziel in einem inkonsistenten Zustand befinden, wodurch ein weiteres Debuggen unzuverlässig wäre.)</span><span class="sxs-lookup"><span data-stu-id="61a6a-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61a6a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61a6a-114">Requirements</span></span>  
 <span data-ttu-id="61a6a-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61a6a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61a6a-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61a6a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61a6a-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61a6a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61a6a-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61a6a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a6a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61a6a-119">See Also</span></span>  
 [<span data-ttu-id="61a6a-120">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61a6a-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="61a6a-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="61a6a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
