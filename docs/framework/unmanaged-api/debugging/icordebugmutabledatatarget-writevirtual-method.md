---
title: ICorDebugMutableDataTarget::WriteVirtual-Methode
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fba970de6e5882d3cbe9be17b5b49be5a3e81aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171651"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="a28e9-102">ICorDebugMutableDataTarget::WriteVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="a28e9-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="a28e9-103">Schreibt Speicher in den Prozessadressraum.</span><span class="sxs-lookup"><span data-stu-id="a28e9-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a28e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a28e9-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a28e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a28e9-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="a28e9-106">[in] Die Adresse, an die der Inhalt von `pBuffer` geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="a28e9-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="a28e9-107">[in] Ein Zeiger auf ein Bytearray, das die zu schreibenden Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="a28e9-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="a28e9-108">[in] Die Anzahl von Bytes in `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="a28e9-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a28e9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a28e9-109">Return Value</span></span>  
 `S_OK` <span data-ttu-id="a28e9-110">auf Erfolg oder einen anderen `HRESULT` bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="a28e9-110">on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a28e9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a28e9-111">Remarks</span></span>  
 <span data-ttu-id="a28e9-112">Wenn Bytes nicht geschrieben werden können, tritt ein Fehler beim Methodenaufruf auf, und es werden keine Bytes im Zieladressraum geändert.</span><span class="sxs-lookup"><span data-stu-id="a28e9-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="a28e9-113">(Andernfalls würde sich das Ziel in einem inkonsistenten Zustand befinden, wodurch ein weiteres Debuggen unzuverlässig wäre.)</span><span class="sxs-lookup"><span data-stu-id="a28e9-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a28e9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a28e9-114">Requirements</span></span>  
 <span data-ttu-id="a28e9-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a28e9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a28e9-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a28e9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a28e9-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a28e9-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a28e9-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a28e9-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a28e9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a28e9-119">See also</span></span>

- [<span data-ttu-id="a28e9-120">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a28e9-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="a28e9-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a28e9-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
