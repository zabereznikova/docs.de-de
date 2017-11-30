---
title: ICorDebugDataTarget::ReadVirtual-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.ReadVirtual Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9b9f0399c05155a9925624e5c9d6bcb6a52f024
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="2cb12-102">ICorDebugDataTarget::ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="2cb12-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="2cb12-103">Ruft einen Block zusammenhängender Arbeitsspeicher ab der angegebenen Adresse, und wird in der bereitgestellte Puffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2cb12-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cb12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cb12-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cb12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cb12-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2cb12-106">[in] Die Startadresse des angeforderten Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="2cb12-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="2cb12-107">[out] Der Puffer, in dem der Arbeitsspeicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2cb12-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="2cb12-108">[in] Die Anzahl der Bytes, die die Zieladresse entnommen werden.</span><span class="sxs-lookup"><span data-stu-id="2cb12-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="2cb12-109">[out] Die Anzahl der gelesenen Bytes tatsächlich aus der Zieladresse.</span><span class="sxs-lookup"><span data-stu-id="2cb12-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="2cb12-110">Dies kann weniger als `bytesRequested`.</span><span class="sxs-lookup"><span data-stu-id="2cb12-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cb12-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cb12-111">Remarks</span></span>  
 <span data-ttu-id="2cb12-112">Wenn das erste Byte (an der angegebenen Startadresse) gelesen werden kann, sollte der Aufruf erfolgreich (um das effiziente Lesen von Datenstrukturen mit selbstbeschreibender Länge, wie Null endende Zeichenfolgen unterstützen) zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2cb12-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cb12-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2cb12-113">Requirements</span></span>  
 <span data-ttu-id="2cb12-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cb12-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cb12-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cb12-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cb12-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cb12-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cb12-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cb12-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb12-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cb12-118">See Also</span></span>  
 [<span data-ttu-id="2cb12-119">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cb12-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="2cb12-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2cb12-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="2cb12-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2cb12-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
