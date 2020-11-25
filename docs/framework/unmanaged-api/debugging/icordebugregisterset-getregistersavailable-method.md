---
title: ICorDebugRegisterSet::GetRegistersAvailable-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
ms.openlocfilehash: d28c130e55cbebf29348752780c03b03c1b8f358
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716992"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="97f84-102">ICorDebugRegisterSet::GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="97f84-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>

<span data-ttu-id="97f84-103">Ruft eine Bitmaske ab, die angibt, welche Register in diesem [icorentbugregisterset](icordebugregisterset-interface.md) zurzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="97f84-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97f84-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97f84-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="97f84-105">Parameters</span></span>  

 `pAvailable`  
 <span data-ttu-id="97f84-106">vorgenommen Eine Bitmaske, die angibt, welche Register zurzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="97f84-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97f84-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97f84-107">Remarks</span></span>  

 <span data-ttu-id="97f84-108">Ein Register ist möglicherweise nicht verfügbar, wenn der Wert für die jeweilige Situation nicht bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="97f84-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="97f84-109">Die zurückgegebene Maske enthält ein Bit für jedes Register (1 << den Register Index).</span><span class="sxs-lookup"><span data-stu-id="97f84-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="97f84-110">Der Bitwert ist 1, wenn das Register verfügbar ist, oder 0, wenn er nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="97f84-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97f84-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="97f84-111">Requirements</span></span>  

 <span data-ttu-id="97f84-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97f84-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97f84-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97f84-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97f84-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97f84-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97f84-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97f84-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f84-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97f84-116">See also</span></span>

- [<span data-ttu-id="97f84-117">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97f84-117">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="97f84-118">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97f84-118">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
