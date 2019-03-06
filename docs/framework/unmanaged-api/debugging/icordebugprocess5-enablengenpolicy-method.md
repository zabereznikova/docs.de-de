---
title: ICorDebugProcess5::EnableNGENPolicy-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d8e848a7664e3573bd369addce2b2f5a8c91821
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481494"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="d2ccb-102">ICorDebugProcess5::EnableNGENPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="d2ccb-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="d2ccb-103">Legt einen Wert, der bestimmt, wie eine Anwendung für systemeigene Images während der Ausführung unter einem verwalteten Debugger geladen.</span><span class="sxs-lookup"><span data-stu-id="d2ccb-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2ccb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2ccb-104">Syntax</span></span>  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2ccb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2ccb-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="d2ccb-106">[in] Ein [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) Konstante, die bestimmt, wie eine Anwendung für systemeigene Images während der Ausführung unter einem verwalteten Debugger geladen.</span><span class="sxs-lookup"><span data-stu-id="d2ccb-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2ccb-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2ccb-107">Remarks</span></span>  
 <span data-ttu-id="d2ccb-108">Wenn die Richtlinie erfolgreich festgelegt wurde, gibt die Methode `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="d2ccb-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="d2ccb-109">Wenn `ePolicy` liegt außerhalb des Bereichs, der durch definierten Enumerationswerte [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), gibt die Methode zurück `E_INVALIDARG` und Aufruf der Methode hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="d2ccb-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="d2ccb-110">Die Methode gibt zurück, wenn die Richtlinie das Native Image Generator (Ngen.exe) kann nicht aktualisiert werden, `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="d2ccb-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="d2ccb-111">Die `ICorDebugProcess5::EnableNGenPolicy` Methode kann zu einem beliebigen Zeitpunkt während der Lebensdauer des Prozesses aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d2ccb-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="d2ccb-112">Die Richtlinie gilt für alle Module, die geladen werden, nachdem die Richtlinie festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="d2ccb-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2ccb-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2ccb-113">Requirements</span></span>  
 <span data-ttu-id="d2ccb-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2ccb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2ccb-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2ccb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2ccb-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2ccb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2ccb-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2ccb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ccb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2ccb-118">See also</span></span>
- [<span data-ttu-id="d2ccb-119">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2ccb-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="d2ccb-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d2ccb-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d2ccb-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d2ccb-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
