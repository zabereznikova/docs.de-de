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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f341098268f735a576bdbc5f0cea52f1a7e14f90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156038"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="cc60f-102">ICorDebugRegisterSet::GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="cc60f-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="cc60f-103">Ruft eine Bitmaske, der angibt, welche Register in diesem [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) sind derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cc60f-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc60f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc60f-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc60f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cc60f-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="cc60f-106">[out] Eine Bitmaske, die angibt, welche Register derzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cc60f-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc60f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc60f-107">Remarks</span></span>  
 <span data-ttu-id="cc60f-108">Ein Register ist möglicherweise nicht verfügbar, wenn der Wert für die angegebene Situation nicht bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cc60f-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="cc60f-109">Die zurückgegebene Maske enthält ein wenig für jedes Register (1 << der Register-Index).</span><span class="sxs-lookup"><span data-stu-id="cc60f-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="cc60f-110">Der Bit-Wert ist 1, wenn es sich bei der Registrierung verfügbar ist, oder 0, wenn sie nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="cc60f-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc60f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cc60f-111">Requirements</span></span>  
 <span data-ttu-id="cc60f-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc60f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc60f-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc60f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc60f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc60f-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cc60f-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cc60f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cc60f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc60f-116">See also</span></span>

- [<span data-ttu-id="cc60f-117">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cc60f-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="cc60f-118">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cc60f-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
