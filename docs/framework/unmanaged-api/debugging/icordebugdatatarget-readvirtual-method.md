---
title: ICorDebugDataTarget::ReadVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bc807906af67350f309a4fc9439899cea328be8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575488"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="60907-102">ICorDebugDataTarget::ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="60907-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="60907-103">Ruft einen Block zusammenhängender Arbeitsspeicher, die beginnend ab der angegebenen Adresse, und der angegebene Puffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="60907-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60907-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60907-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60907-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="60907-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="60907-106">[in] Die Startadresse des angeforderten Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="60907-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="60907-107">[out] Der Puffer, in dem der Arbeitsspeicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="60907-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="60907-108">[in] Die Anzahl der Bytes, die von der Zieladresse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="60907-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="60907-109">[out] Die Anzahl der gelesenen Bytes tatsächlich von der Zieladresse.</span><span class="sxs-lookup"><span data-stu-id="60907-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="60907-110">Dies kann weniger als sein `bytesRequested`.</span><span class="sxs-lookup"><span data-stu-id="60907-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60907-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60907-111">Remarks</span></span>  
 <span data-ttu-id="60907-112">Wenn das erste Byte (an der angegebenen Adresse) gelesen werden kann, sollte der Aufruf erfolgreich (um das effiziente Lesen von Datenstrukturen mit selbstbeschreibend Länge haben, wie Null-terminierte Zeichenfolgen zu unterstützen) zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="60907-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60907-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60907-113">Requirements</span></span>  
 <span data-ttu-id="60907-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60907-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60907-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60907-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60907-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60907-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60907-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60907-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60907-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60907-118">See also</span></span>
- [<span data-ttu-id="60907-119">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60907-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="60907-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="60907-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="60907-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="60907-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
