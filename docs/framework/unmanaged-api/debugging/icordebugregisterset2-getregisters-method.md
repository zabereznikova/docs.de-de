---
title: ICorDebugRegisterSet2::GetRegisters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
ms.openlocfilehash: b7a356d80d63fae65191bbf4fc0a23d7e02004c9
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378232"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="4a9f8-102">ICorDebugRegisterSet2::GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="4a9f8-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="4a9f8-103">Ruft den Wert der einzelnen Register (für die Plattform, auf der der Code gerade ausgeführt wird) ab, die von der angegebenen Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a9f8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a9f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a9f8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a9f8-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="4a9f8-106">in Die Größe des Arrays in Bytes `mask` .</span><span class="sxs-lookup"><span data-stu-id="4a9f8-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="4a9f8-107">in Ein Bytearray, das jedem Bit entspricht, das einem Register entspricht.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="4a9f8-108">Wenn das Bit 1 ist, wird der zugehörige Registrierungs Wert abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="4a9f8-109">in Die Anzahl der abzurufenden Registrierungs Werte.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="4a9f8-110">vorgenommen Ein Array von- `CORDB_REGISTER` Objekten, von denen jede den Wert eines Register empfängt.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a9f8-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a9f8-111">Remarks</span></span>  
 <span data-ttu-id="4a9f8-112">Die- `GetRegisters` Methode gibt ein Array von Werten aus den Registern zurück, die von der Maske angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="4a9f8-113">Das Array enthält keine Werte von Registern, deren Masken Bit nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="4a9f8-114">Folglich muss die Größe des `regBuffer` Arrays mit der Anzahl von 1 in der Maske identisch sein.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="4a9f8-115">Wenn der Wert von `regCount` zu klein für die Anzahl der von der Maske festgelegten Register ist, werden die Werte der höher nummerierten Register von der Menge abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="4a9f8-116">Wenn `regCount` zu groß ist, werden die `regBuffer` nicht verwendeten Elemente unverändert geändert.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="4a9f8-117">Wenn ein nicht verfügbares Register durch die Maske angegeben wird, wird für dieses Register ein unbestimmter Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="4a9f8-118">Die- `ICorDebugRegisterSet2::GetRegisters` Methode ist für Plattformen erforderlich, die über mehr als 64 Register verfügen.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="4a9f8-119">Beispielsweise hat ia64 128 allgemeine Register und 128 Gleit Komma Register, sodass Sie mehr als 64 Bits in der Bitmaske benötigen.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="4a9f8-120">Wenn Sie nicht über mehr als 64 Register verfügen, wie es bei Plattformen wie z. b. x86 der Fall ist, `GetRegisters` übersetzt die Methode tatsächlich lediglich die Bytes im `mask` Bytearray in ein `ULONG64` und ruft dann die [ICorDebugRegisterSet:: GetRegisters](icordebugregisterset-getregisters-method.md) -Methode auf, die die `ULONG64` Maske annimmt.</span><span class="sxs-lookup"><span data-stu-id="4a9f8-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a9f8-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4a9f8-121">Requirements</span></span>  
 <span data-ttu-id="4a9f8-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a9f8-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a9f8-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a9f8-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a9f8-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a9f8-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a9f8-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a9f8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a9f8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a9f8-126">See also</span></span>

- [<span data-ttu-id="4a9f8-127">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a9f8-127">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="4a9f8-128">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a9f8-128">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
