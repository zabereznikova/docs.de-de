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
ms.openlocfilehash: c598491acd27223a8a41234ddf2c6b8e6f005d52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423142"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="de287-102">ICorDebugProcess5::EnableNGENPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="de287-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="de287-103">Legt einen Wert, der bestimmt, wie eine Anwendung während der Ausführung unter einem verwalteten Debugger systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="de287-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de287-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de287-104">Syntax</span></span>  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de287-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="de287-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="de287-106">[in] Ein [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) Konstante, die bestimmt, wie eine Anwendung während der Ausführung unter einem verwalteten Debugger systemeigene Abbilder lädt.</span><span class="sxs-lookup"><span data-stu-id="de287-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de287-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de287-107">Remarks</span></span>  
 <span data-ttu-id="de287-108">Wenn die Richtlinie erfolgreich festgelegt ist, gibt die Methode `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="de287-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="de287-109">Wenn `ePolicy` liegt außerhalb des Bereichs der Enumerationswerte, die durch definierten [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), der Methodenrückgabe `E_INVALIDARG` und dem Aufruf der Methode hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="de287-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="de287-110">Wenn die Richtlinie für die Native Image Generator (Ngen.exe) nicht aktualisiert werden kann, gibt die Methode `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="de287-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="de287-111">Die `ICorDebugProcess5::EnableNGenPolicy` Methode kann zu einem beliebigen Zeitpunkt während der Lebensdauer des Prozesses aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="de287-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="de287-112">Die Richtlinie gilt für Module, die geladen werden, nachdem die Richtlinie festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="de287-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de287-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de287-113">Requirements</span></span>  
 <span data-ttu-id="de287-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de287-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de287-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de287-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de287-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de287-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de287-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de287-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de287-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de287-118">See Also</span></span>  
 [<span data-ttu-id="de287-119">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de287-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="de287-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="de287-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="de287-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="de287-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
