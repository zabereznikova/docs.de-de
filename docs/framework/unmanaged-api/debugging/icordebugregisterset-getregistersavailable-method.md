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
ms.openlocfilehash: 9d8bd6ab13fa408fd7390aaeb76baee274742f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137700"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="97b5e-102">ICorDebugRegisterSet::GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="97b5e-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="97b5e-103">Ruft eine Bitmaske ab, die angibt, welche Register in diesem [icorentbugregisterset](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) zurzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="97b5e-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97b5e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97b5e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="97b5e-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="97b5e-106">vorgenommen Eine Bitmaske, die angibt, welche Register zurzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="97b5e-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97b5e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97b5e-107">Remarks</span></span>  
 <span data-ttu-id="97b5e-108">Ein Register ist möglicherweise nicht verfügbar, wenn der Wert für die jeweilige Situation nicht bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="97b5e-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="97b5e-109">Die zurückgegebene Maske enthält ein Bit für jedes Register (1 < < dem Register Index).</span><span class="sxs-lookup"><span data-stu-id="97b5e-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="97b5e-110">Der Bitwert ist 1, wenn das Register verfügbar ist, oder 0, wenn er nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="97b5e-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97b5e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97b5e-111">Requirements</span></span>  
 <span data-ttu-id="97b5e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97b5e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97b5e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97b5e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97b5e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97b5e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97b5e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97b5e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b5e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97b5e-116">See also</span></span>

- [<span data-ttu-id="97b5e-117">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97b5e-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="97b5e-118">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97b5e-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
