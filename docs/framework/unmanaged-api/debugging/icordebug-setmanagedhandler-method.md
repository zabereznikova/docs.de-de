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
ms.openlocfilehash: 88a007654646ba42ebcaf1b42e002282a1040c7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134054"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="d83ea-102">ICorDebug::SetManagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="d83ea-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="d83ea-103">Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="d83ea-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d83ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d83ea-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d83ea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d83ea-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="d83ea-106">in Ein Zeiger auf ein [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) -Objekt, das das Ereignishandlerobjekt ist.</span><span class="sxs-lookup"><span data-stu-id="d83ea-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d83ea-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d83ea-107">Remarks</span></span>  
 <span data-ttu-id="d83ea-108">`SetManagedHandler` muss zur Erstellungszeit aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d83ea-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="d83ea-109">Wenn die `ICorDebugManagedCallback`-Implementierung nicht genügend Schnittstellen zum Verarbeiten von Debugereignissen für die zu debuggende Anwendung enthält, gibt `SetManagedHandler` ein HRESULT von E_NOINTERFACE zurück.</span><span class="sxs-lookup"><span data-stu-id="d83ea-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d83ea-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d83ea-110">Requirements</span></span>  
 <span data-ttu-id="d83ea-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d83ea-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d83ea-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d83ea-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d83ea-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d83ea-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d83ea-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d83ea-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d83ea-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d83ea-115">See also</span></span>

- [<span data-ttu-id="d83ea-116">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d83ea-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
