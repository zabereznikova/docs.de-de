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
ms.openlocfilehash: 112d530c765fc74ab4ea767cb3168977d1b45f47
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138366"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="3bd6f-102">ICorDebugRegisterSet::GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="3bd6f-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="3bd6f-103">Ruft den Wert der einzelnen Register (auf dem momentan ausgeführten Code) ab, der durch die Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bd6f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bd6f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bd6f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3bd6f-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="3bd6f-106">in Eine Bitmaske, die angibt, welche Registerwerte abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="3bd6f-107">Jedes Bit entspricht einem Register.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="3bd6f-108">Wenn ein Bit auf 1 festgelegt ist, wird der Wert des Registers abgerufen. Andernfalls wird der Wert des Registers nicht abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="3bd6f-109">in Die Anzahl der abzurufenden Registrierungs Werte.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="3bd6f-110">vorgenommen Ein Array von `CORDB_REGISTER`-Objekten, von denen jede den Wert eines Register erhält.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bd6f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3bd6f-111">Remarks</span></span>  
 <span data-ttu-id="3bd6f-112">Die Größe des Arrays sollte gleich der Anzahl von Bits sein, die in der Bitmaske auf eins festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="3bd6f-113">Der `regCount`-Parameter gibt die Anzahl der Elemente im Puffer an, die die Registerwerte erhalten.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="3bd6f-114">Wenn der `regCount` Wert für die Anzahl der von der Maske festgelegten Register zu klein ist, werden die höheren nummerierten Register von der Menge abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="3bd6f-115">Wenn der `regCount` Wert zu groß ist, werden die nicht verwendeten `regBuffer` Elemente unverändert geändert.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="3bd6f-116">Wenn die Bitmaske ein nicht verfügbares Register angibt, gibt `GetRegisters` einen unbestimmten Wert für dieses Register zurück.</span><span class="sxs-lookup"><span data-stu-id="3bd6f-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bd6f-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3bd6f-117">Requirements</span></span>  
 <span data-ttu-id="3bd6f-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bd6f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bd6f-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3bd6f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3bd6f-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bd6f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bd6f-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bd6f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd6f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bd6f-122">See also</span></span>

- [<span data-ttu-id="3bd6f-123">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bd6f-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="3bd6f-124">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bd6f-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
