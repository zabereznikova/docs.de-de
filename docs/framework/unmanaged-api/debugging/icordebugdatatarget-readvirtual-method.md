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
ms.openlocfilehash: 2d9e619e4176633074242521133d42f191f140ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412190"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="6b4e8-102">ICorDebugDataTarget::ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="6b4e8-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="6b4e8-103">Ruft einen Block zusammenhängender Arbeitsspeicher ab der angegebenen Adresse, und wird in der bereitgestellte Puffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6b4e8-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b4e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b4e8-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b4e8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b4e8-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="6b4e8-106">[in] Die Startadresse des angeforderten Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="6b4e8-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="6b4e8-107">[out] Der Puffer, in dem der Arbeitsspeicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6b4e8-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="6b4e8-108">[in] Die Anzahl der Bytes, die die Zieladresse entnommen werden.</span><span class="sxs-lookup"><span data-stu-id="6b4e8-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="6b4e8-109">[out] Die Anzahl der gelesenen Bytes tatsächlich aus der Zieladresse.</span><span class="sxs-lookup"><span data-stu-id="6b4e8-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="6b4e8-110">Dies kann weniger als `bytesRequested`.</span><span class="sxs-lookup"><span data-stu-id="6b4e8-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b4e8-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b4e8-111">Remarks</span></span>  
 <span data-ttu-id="6b4e8-112">Wenn das erste Byte (an der angegebenen Startadresse) gelesen werden kann, sollte der Aufruf erfolgreich (um das effiziente Lesen von Datenstrukturen mit selbstbeschreibender Länge, wie Null endende Zeichenfolgen unterstützen) zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6b4e8-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b4e8-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b4e8-113">Requirements</span></span>  
 <span data-ttu-id="6b4e8-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b4e8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b4e8-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b4e8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b4e8-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b4e8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b4e8-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b4e8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b4e8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b4e8-118">See Also</span></span>  
 [<span data-ttu-id="6b4e8-119">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b4e8-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="6b4e8-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6b4e8-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6b4e8-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6b4e8-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
