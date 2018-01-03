---
title: ICorDebugMutableDataTarget::WriteVirtual-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 303c5737ebd241b8f2f756de0ed5426787de3bd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="77038-102">ICorDebugMutableDataTarget::WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="77038-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="77038-103">Schreibt Speicher in den Prozessadressraum.</span><span class="sxs-lookup"><span data-stu-id="77038-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77038-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77038-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77038-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="77038-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="77038-106">[in] Die Adresse, an die der Inhalt von `pBuffer` geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="77038-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="77038-107">[in] Ein Zeiger auf ein Bytearray, das die zu schreibenden Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="77038-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="77038-108">[in] Die Anzahl von Bytes in `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="77038-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77038-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="77038-109">Return Value</span></span>  
 <span data-ttu-id="77038-110">`S_OK` bei erfolgreichem Verlauf oder ein anderes `HRESULT` im Fall eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="77038-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77038-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77038-111">Remarks</span></span>  
 <span data-ttu-id="77038-112">Wenn Bytes nicht geschrieben werden können, tritt ein Fehler beim Methodenaufruf auf, und es werden keine Bytes im Zieladressraum geändert.</span><span class="sxs-lookup"><span data-stu-id="77038-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="77038-113">(Andernfalls würde sich das Ziel in einem inkonsistenten Zustand befinden, wodurch ein weiteres Debuggen unzuverlässig wäre.)</span><span class="sxs-lookup"><span data-stu-id="77038-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77038-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77038-114">Requirements</span></span>  
 <span data-ttu-id="77038-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77038-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77038-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77038-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77038-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77038-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77038-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77038-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77038-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77038-119">See Also</span></span>  
 [<span data-ttu-id="77038-120">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77038-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="77038-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="77038-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
