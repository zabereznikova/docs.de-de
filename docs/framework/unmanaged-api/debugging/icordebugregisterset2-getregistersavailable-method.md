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
ms.openlocfilehash: cb56ea817d4045c19793a6290d68ae8b6236f14a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712316"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="edbf9-102">ICorDebugRegisterSet2::GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="edbf9-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>

<span data-ttu-id="edbf9-103">Ruft ein Bytearray ab, das eine Bitmap der verfügbaren Register bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="edbf9-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edbf9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="edbf9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edbf9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="edbf9-105">Parameters</span></span>  

 `numChunks`  
 <span data-ttu-id="edbf9-106">[in] Die Größe des `availableRegChunks`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="edbf9-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="edbf9-107">vorgenommen Ein Bytearray, das jedem Bit entspricht, das einem Register entspricht.</span><span class="sxs-lookup"><span data-stu-id="edbf9-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="edbf9-108">Wenn ein Register verfügbar ist, wird das entsprechende Bit des Registrierungs Satzes festgelegt.</span><span class="sxs-lookup"><span data-stu-id="edbf9-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edbf9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="edbf9-109">Remarks</span></span>  

 <span data-ttu-id="edbf9-110">Die Werte der CorDebugRegister-Enumeration geben die Register verschiedener Mikroprozessoren an.</span><span class="sxs-lookup"><span data-stu-id="edbf9-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="edbf9-111">Die oberen fünf Bits der einzelnen Werte sind der Index im `availableRegChunks` Bytearray.</span><span class="sxs-lookup"><span data-stu-id="edbf9-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="edbf9-112">Die unteren drei Bits der einzelnen Werte identifizieren die Bitposition innerhalb des indizierten bytes.</span><span class="sxs-lookup"><span data-stu-id="edbf9-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="edbf9-113">Wenn ein `CorDebugRegister` Wert angegeben ist, der ein bestimmtes Register angibt, wird die Position des Registers in der Maske wie folgt bestimmt:</span><span class="sxs-lookup"><span data-stu-id="edbf9-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="edbf9-114">Extrahieren Sie den Index, der für den Zugriff auf das richtige Byte im Array erforderlich ist `availableRegChunks` :</span><span class="sxs-lookup"><span data-stu-id="edbf9-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="edbf9-115">`CorDebugRegister` Wert >> 3</span><span class="sxs-lookup"><span data-stu-id="edbf9-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="edbf9-116">Extrahieren Sie die Bitposition innerhalb des indizierten bytes, wobei Bit NULL das am wenigsten bedeutende Bit ist:</span><span class="sxs-lookup"><span data-stu-id="edbf9-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="edbf9-117">`CorDebugRegister` Wert & 7</span><span class="sxs-lookup"><span data-stu-id="edbf9-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edbf9-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="edbf9-118">Requirements</span></span>  

 <span data-ttu-id="edbf9-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edbf9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edbf9-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edbf9-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edbf9-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edbf9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edbf9-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edbf9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edbf9-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="edbf9-123">See also</span></span>

- [<span data-ttu-id="edbf9-124">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edbf9-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="edbf9-125">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edbf9-125">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
