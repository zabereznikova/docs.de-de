---
title: ICorDebugRegisterSet2::GetRegistersAvailable-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
ms.openlocfilehash: 00c9939b25f395010f6ea5832b405c3e9928a223
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792026"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="8e12b-102">ICorDebugRegisterSet2::GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="8e12b-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="8e12b-103">Ruft ein Bytearray ab, das eine Bitmap der verfügbaren Register bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8e12b-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e12b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e12b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e12b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8e12b-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="8e12b-106">[in] Die Größe des `availableRegChunks`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="8e12b-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="8e12b-107">vorgenommen Ein Bytearray, das jedem Bit entspricht, das einem Register entspricht.</span><span class="sxs-lookup"><span data-stu-id="8e12b-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="8e12b-108">Wenn ein Register verfügbar ist, wird das entsprechende Bit des Registrierungs Satzes festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8e12b-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e12b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e12b-109">Remarks</span></span>  
 <span data-ttu-id="8e12b-110">Die Werte der CorDebugRegister-Enumeration geben die Register verschiedener Mikroprozessoren an.</span><span class="sxs-lookup"><span data-stu-id="8e12b-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="8e12b-111">Die oberen fünf Bits jedes Werts sind der Index für das `availableRegChunks` Bytearray.</span><span class="sxs-lookup"><span data-stu-id="8e12b-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="8e12b-112">Die unteren drei Bits der einzelnen Werte identifizieren die Bitposition innerhalb des indizierten bytes.</span><span class="sxs-lookup"><span data-stu-id="8e12b-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="8e12b-113">Bei einem `CorDebugRegister` Wert, der ein bestimmtes Register angibt, wird die Position des Registers in der Maske wie folgt bestimmt:</span><span class="sxs-lookup"><span data-stu-id="8e12b-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="8e12b-114">Extrahieren Sie den Index, der für den Zugriff auf das richtige Byte im `availableRegChunks` Array erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="8e12b-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="8e12b-115">`CorDebugRegister` Wert > > 3</span><span class="sxs-lookup"><span data-stu-id="8e12b-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="8e12b-116">Extrahieren Sie die Bitposition innerhalb des indizierten bytes, wobei Bit NULL das am wenigsten bedeutende Bit ist:</span><span class="sxs-lookup"><span data-stu-id="8e12b-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="8e12b-117">`CorDebugRegister` Wert & 7</span><span class="sxs-lookup"><span data-stu-id="8e12b-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e12b-118">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e12b-118">Requirements</span></span>  
 <span data-ttu-id="8e12b-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e12b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e12b-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e12b-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e12b-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e12b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e12b-122">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e12b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e12b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e12b-123">See also</span></span>

- [<span data-ttu-id="8e12b-124">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e12b-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="8e12b-125">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e12b-125">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
