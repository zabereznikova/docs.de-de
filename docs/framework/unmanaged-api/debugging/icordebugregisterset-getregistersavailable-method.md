---
title: ICorDebugRegisterSet::GetRegistersAvailable-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fd7ff2b711d81ba1fe8fda9422587ec265dd88dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="fb544-102">ICorDebugRegisterSet::GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="fb544-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="fb544-103">Ruft eine Bitmaske, die angibt, welche Register in diesem [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) sind derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb544-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb544-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb544-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb544-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fb544-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="fb544-106">[out] Eine Bitmaske, die angibt, welche Register derzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fb544-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb544-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb544-107">Remarks</span></span>  
 <span data-ttu-id="fb544-108">Ein Registers ist möglicherweise nicht verfügbar, wenn der Wert für die angegebene Situation bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb544-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="fb544-109">Die zurückgegebene Maske enthält ein bit für jedes Register (1 << Register Index).</span><span class="sxs-lookup"><span data-stu-id="fb544-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="fb544-110">Der Bitwert ist 1, wenn die Registrierung verfügbar ist, oder 0, wenn er nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fb544-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb544-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb544-111">Requirements</span></span>  
 <span data-ttu-id="fb544-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb544-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb544-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb544-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb544-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb544-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb544-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb544-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb544-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb544-116">See Also</span></span>  
 [<span data-ttu-id="fb544-117">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb544-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="fb544-118">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb544-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
