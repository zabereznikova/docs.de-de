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
ms.openlocfilehash: b137b956e06a2b2954918e4024860f9b234e7583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792105"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="2813e-102">ICorDebugRegisterSet::GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="2813e-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="2813e-103">Ruft eine Bitmaske ab, die angibt, welche Register in diesem [icorentbugregisterset](icordebugregisterset-interface.md) zurzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2813e-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2813e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2813e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2813e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2813e-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="2813e-106">vorgenommen Eine Bitmaske, die angibt, welche Register zurzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2813e-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2813e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2813e-107">Remarks</span></span>  
 <span data-ttu-id="2813e-108">Ein Register ist möglicherweise nicht verfügbar, wenn der Wert für die jeweilige Situation nicht bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2813e-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="2813e-109">Die zurückgegebene Maske enthält ein Bit für jedes Register (1 < < dem Register Index).</span><span class="sxs-lookup"><span data-stu-id="2813e-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="2813e-110">Der Bitwert ist 1, wenn das Register verfügbar ist, oder 0, wenn er nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2813e-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2813e-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2813e-111">Requirements</span></span>  
 <span data-ttu-id="2813e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2813e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2813e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2813e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2813e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2813e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2813e-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2813e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2813e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2813e-116">See also</span></span>

- [<span data-ttu-id="2813e-117">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2813e-117">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="2813e-118">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2813e-118">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
