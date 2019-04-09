---
title: ICorDebug::SetManagedHandler-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f30089879f2d023c8fb04b52e75b2942da2a83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130155"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="d48ee-102">ICorDebug::SetManagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="d48ee-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="d48ee-103">Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="d48ee-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d48ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d48ee-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d48ee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d48ee-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="d48ee-106">[in] Ein Zeiger auf ein [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) Objekt, das das Ereignishandlerobjekt ist.</span><span class="sxs-lookup"><span data-stu-id="d48ee-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d48ee-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d48ee-107">Remarks</span></span>  
 `SetManagedHandler` <span data-ttu-id="d48ee-108">muss zum Zeitpunkt der Erstellung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d48ee-108">must be called at creation time.</span></span>  
  
 <span data-ttu-id="d48ee-109">Wenn die `ICorDebugManagedCallback` Implementierung enthält keine ausreichende Schnittstellen um Debugereignisse, die für die Anwendung zu behandeln, die gedebuggt wird, `SetManagedHandler` gibt ein HRESULT von E_NOINTERFACE zurück.</span><span class="sxs-lookup"><span data-stu-id="d48ee-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d48ee-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d48ee-110">Requirements</span></span>  
 <span data-ttu-id="d48ee-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d48ee-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d48ee-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d48ee-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d48ee-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d48ee-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d48ee-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d48ee-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d48ee-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d48ee-115">See also</span></span>

- [<span data-ttu-id="d48ee-116">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d48ee-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
