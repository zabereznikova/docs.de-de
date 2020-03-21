---
title: ICorDebugRegisterSet::GetRegisters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 32e899622b9c649a08e3bca1b6645f70dcbcbb19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178544"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="89a74-102">ICorDebugRegisterSet::GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="89a74-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="89a74-103">Ruft den Wert jedes Registers ab (auf dem Computer, der derzeit Code ausführt), der von der Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="89a74-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a74-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89a74-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89a74-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="89a74-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="89a74-106">[in] Eine Bitmaske, die angibt, welche Registerwerte abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89a74-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="89a74-107">Jedes Bit entspricht einem Register.</span><span class="sxs-lookup"><span data-stu-id="89a74-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="89a74-108">Wenn ein Bit auf einbit festgelegt ist, wird der Wert des Registers abgerufen. Andernfalls wird der Wert des Registers nicht abgerufen.</span><span class="sxs-lookup"><span data-stu-id="89a74-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="89a74-109">[in] Die Anzahl der registerwerte, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89a74-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="89a74-110">[out] Ein Array `CORDB_REGISTER` von Objekten, von denen jedes den Wert eines Registers empfängt.</span><span class="sxs-lookup"><span data-stu-id="89a74-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89a74-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="89a74-111">Remarks</span></span>  
 <span data-ttu-id="89a74-112">Die Größe des Arrays sollte gleich der Anzahl der Bits sein, die in der Bitmaske auf eins festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="89a74-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="89a74-113">Der `regCount` Parameter gibt die Anzahl der Elemente im Puffer an, die die Registerwerte empfangen.</span><span class="sxs-lookup"><span data-stu-id="89a74-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="89a74-114">Wenn `regCount` der Wert für die Anzahl der register, die durch die Maske angegeben werden, zu klein ist, werden die höheren nummerierten Register aus dem Satz abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="89a74-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="89a74-115">Wenn `regCount` der Wert zu groß `regBuffer` ist, werden die nicht verwendeten Elemente nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="89a74-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="89a74-116">Wenn die Bitmaske ein Register angibt, das nicht verfügbar ist, `GetRegisters` gibt ein unbestimmter Wert für dieses Register zurück.</span><span class="sxs-lookup"><span data-stu-id="89a74-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a74-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="89a74-117">Requirements</span></span>  
 <span data-ttu-id="89a74-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89a74-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89a74-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89a74-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89a74-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89a74-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89a74-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89a74-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a74-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89a74-122">See also</span></span>

- [<span data-ttu-id="89a74-123">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89a74-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="89a74-124">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89a74-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
