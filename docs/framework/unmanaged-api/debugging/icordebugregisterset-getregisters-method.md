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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee56a7f343de999d68a71d9eac04eed6e06b444e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568893"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="dfaa7-102">ICorDebugRegisterSet::GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="dfaa7-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="dfaa7-103">Ruft den Wert jedes Register (auf dem Computer, die gerade Code ausführt) ab, das durch die Bitmaske angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfaa7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfaa7-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dfaa7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dfaa7-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="dfaa7-106">[in] Eine Bitmaske, die angibt, welche Register Werte abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="dfaa7-107">Jedes Bit entspricht einer registrieren.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="dfaa7-108">Wenn ein bit auf 1 festgelegt ist, wird der Wert des Registers abgerufen. Andernfalls wird der Wert des Registers nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="dfaa7-109">[in] Die Anzahl der Registerwerte abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="dfaa7-110">[out] Ein Array von `CORDB_REGISTER` Objekte, von denen jede einen Wert eines Registers empfängt.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfaa7-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dfaa7-111">Remarks</span></span>  
 <span data-ttu-id="dfaa7-112">Die Größe des Arrays sollte gleich der Anzahl der Bits, die auf einen in der Bitmaske festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="dfaa7-113">Die `regCount` Parameter gibt die Anzahl der Elemente im Puffer, der die Registerwerte empfängt.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="dfaa7-114">Wenn die `regCount` Wert ist zu klein für die Anzahl von Registern der Maske, die höhere nummerierten Register aus dem Satz gekürzt.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="dfaa7-115">Wenn die `regCount` Wert ist zu groß ist, die nicht verwendeten `regBuffer` Elemente nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="dfaa7-116">Wenn die Bitmaske ein Registers angibt, der nicht verfügbar ist, `GetRegisters` gibt einen unbestimmten Wert für diese registrieren.</span><span class="sxs-lookup"><span data-stu-id="dfaa7-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfaa7-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dfaa7-117">Requirements</span></span>  
 <span data-ttu-id="dfaa7-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfaa7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfaa7-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfaa7-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfaa7-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfaa7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfaa7-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfaa7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfaa7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfaa7-122">See also</span></span>
- [<span data-ttu-id="dfaa7-123">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dfaa7-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="dfaa7-124">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dfaa7-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
