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
ms.openlocfilehash: 20cea94961a250c3981d892910da1dcee20a060b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783742"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="8c9c5-102">ICorDebugDataTarget::ReadVirtual-Methode</span><span class="sxs-lookup"><span data-stu-id="8c9c5-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="8c9c5-103">Ruft einen Block von zusammenhängenden Arbeitsspeicher ab, der bei der angegebenen Adresse beginnt, und gibt ihn im angegebenen Puffer zurück.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c9c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c9c5-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c9c5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8c9c5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="8c9c5-106">in Die Startadresse des angeforderten Speichers.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="8c9c5-107">vorgenommen Der Puffer, in dem der Arbeitsspeicher gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="8c9c5-108">in Die Anzahl der Bytes, die von der Zieladresse abgeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="8c9c5-109">vorgenommen Die Anzahl der tatsächlich von der Zieladresse gelesenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="8c9c5-110">Dies kann weniger als `bytesRequested`sein.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c9c5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c9c5-111">Remarks</span></span>  
 <span data-ttu-id="8c9c5-112">Wenn das erste Byte (an der angegebenen Startadresse) gelesen werden kann, sollte der-Befehl einen Erfolg zurückgeben (um das effiziente Lesen von Datenstrukturen mit selbst beschreibender Länge zu unterstützen, wie z. b. auf NULL endende Zeichen folgen).</span><span class="sxs-lookup"><span data-stu-id="8c9c5-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c9c5-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c9c5-113">Requirements</span></span>  
 <span data-ttu-id="8c9c5-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c9c5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c9c5-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c9c5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c9c5-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c9c5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c9c5-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c9c5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c9c5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c9c5-118">See also</span></span>

- [<span data-ttu-id="8c9c5-119">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c9c5-119">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="8c9c5-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8c9c5-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8c9c5-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8c9c5-121">Debugging</span></span>](index.md)
