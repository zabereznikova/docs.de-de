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
ms.openlocfilehash: 74eef0c1ec456d647e5a58e5009d2c77e5002289
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378289"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="a5907-102">ICorDebugRegisterSet::GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="a5907-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="a5907-103">Ruft eine Bitmaske ab, die angibt, welche Register in diesem [icorentbugregisterset](icordebugregisterset-interface.md) zurzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a5907-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5907-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5907-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5907-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5907-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="a5907-106">vorgenommen Eine Bitmaske, die angibt, welche Register zurzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a5907-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5907-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5907-107">Remarks</span></span>  
 <span data-ttu-id="a5907-108">Ein Register ist möglicherweise nicht verfügbar, wenn der Wert für die jeweilige Situation nicht bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a5907-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="a5907-109">Die zurückgegebene Maske enthält ein Bit für jedes Register (1 << den Register Index).</span><span class="sxs-lookup"><span data-stu-id="a5907-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="a5907-110">Der Bitwert ist 1, wenn das Register verfügbar ist, oder 0, wenn er nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a5907-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5907-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a5907-111">Requirements</span></span>  
 <span data-ttu-id="a5907-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5907-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5907-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5907-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5907-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5907-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5907-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5907-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5907-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5907-116">See also</span></span>

- [<span data-ttu-id="a5907-117">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5907-117">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="a5907-118">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5907-118">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
