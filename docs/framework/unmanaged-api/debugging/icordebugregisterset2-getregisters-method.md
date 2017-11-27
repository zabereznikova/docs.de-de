---
title: ICorDebugRegisterSet2::GetRegisters-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2.GetRegisters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f9deccff09c255b339a22af711906baf23d7df9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="e4147-102">ICorDebugRegisterSet2::GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="e4147-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="e4147-103">Ruft den Wert jedes Register (für die Plattform, auf der Code derzeit ausgeführt wird), die von der angegebenen Bitmaske angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e4147-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4147-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4147-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4147-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4147-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="e4147-106">[in] Die Größe in Bytes, der die `mask` Array.</span><span class="sxs-lookup"><span data-stu-id="e4147-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="e4147-107">[in] Ein Array von Bytes, von denen jedes Bit eines Registers entspricht.</span><span class="sxs-lookup"><span data-stu-id="e4147-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="e4147-108">Wenn das Bit 1 ist, wird der entsprechende Wert des Registers abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e4147-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="e4147-109">[in] Die Anzahl der Registerwerte abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e4147-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="e4147-110">[out] Ein Array von `CORDB_REGISTER` Objekte, von denen jede den Wert eines Registers empfängt.</span><span class="sxs-lookup"><span data-stu-id="e4147-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4147-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4147-111">Remarks</span></span>  
 <span data-ttu-id="e4147-112">Die `GetRegisters` Methode gibt ein Array von Werten aus dem Register, die von der Maske angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e4147-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="e4147-113">Das Array enthält keine Werte von Registern, deren Maskenbit nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4147-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="e4147-114">Somit die Größe der `regBuffer` Arrays gleich der Anzahl von 1 in der Maske sein muss.</span><span class="sxs-lookup"><span data-stu-id="e4147-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="e4147-115">Wenn der Wert des `regCount` ist zu klein für die angegebene Anzahl von Registern durch die Maske, die Werte der höher nummerierten Register aus dem Satz abgeschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="e4147-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="e4147-116">Wenn `regCount` ist zu groß ist, der nicht verwendeten `regBuffer` Elemente nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e4147-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="e4147-117">Wenn eine Registrierung nicht verfügbar, die von der Maske angegeben ist, wird für, die sich registrieren ein unbestimmter Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e4147-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="e4147-118">Die `ICorDebugRegisterSet2::GetRegisters` Methode ist erforderlich für Plattformen, die mehr als 64 Registern haben.</span><span class="sxs-lookup"><span data-stu-id="e4147-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="e4147-119">Beispielsweise weist IA64 128 Allzweckregister und 128 Gleitkommaregister, daher Sie mehr als 64-Bit in der Bitmaske müssen.</span><span class="sxs-lookup"><span data-stu-id="e4147-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="e4147-120">Wenn Sie nicht mehr als 64 Registern verfügen wie die Groß-/Kleinschreibung auf Plattformen wie X86, ist die `GetRegisters` Methode übersetzt tatsächlich nur die Bytes in der `mask` Bytearray, in eine `ULONG64` und ruft dann die [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) Methode, die akzeptiert die `ULONG64` Maske.</span><span class="sxs-lookup"><span data-stu-id="e4147-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4147-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4147-121">Requirements</span></span>  
 <span data-ttu-id="e4147-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4147-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4147-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4147-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4147-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4147-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4147-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4147-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4147-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4147-126">See Also</span></span>  
 [<span data-ttu-id="e4147-127">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4147-127">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="e4147-128">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4147-128">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
