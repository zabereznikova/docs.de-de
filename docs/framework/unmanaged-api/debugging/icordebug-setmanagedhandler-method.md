---
title: ICorDebug::SetManagedHandler-Methode
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
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dde32b6a8251474c4254e35a3a1ba3ba3bafcb8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="922cf-102">ICorDebug::SetManagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="922cf-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="922cf-103">Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="922cf-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="922cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="922cf-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="922cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="922cf-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="922cf-106">[in] Ein Zeiger auf ein [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) -Objekt, das das Ereignishandlerobjekt fungiert.</span><span class="sxs-lookup"><span data-stu-id="922cf-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="922cf-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="922cf-107">Remarks</span></span>  
 <span data-ttu-id="922cf-108">`SetManagedHandler`muss zum Zeitpunkt der Erstellung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="922cf-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="922cf-109">Wenn die `ICorDebugManagedCallback` Implementierung enthält keine ausreichende Schnittstellen um Debugereignisse für die Anwendung zu behandeln, der debuggt wird, `SetManagedHandler` gibt ein HRESULT E_NOINTERFACE zurück.</span><span class="sxs-lookup"><span data-stu-id="922cf-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="922cf-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="922cf-110">Requirements</span></span>  
 <span data-ttu-id="922cf-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="922cf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="922cf-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="922cf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="922cf-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="922cf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="922cf-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="922cf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="922cf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="922cf-115">See Also</span></span>  
 [<span data-ttu-id="922cf-116">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="922cf-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
