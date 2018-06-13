---
title: ICorDebugManagedCallback::LoadModule-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbf538f066058b4f80d8cfd6cdf1a79683c79be9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413416"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="94a6e-102">ICorDebugManagedCallback::LoadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="94a6e-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="94a6e-103">Benachrichtigt den Debugger, dass eine common Language Runtime (CLR)-Modul erfolgreich geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="94a6e-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94a6e-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94a6e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="94a6e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="94a6e-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der das Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="94a6e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="94a6e-107">[in] Ein Zeiger auf ein ICorDebugModule-Objekt, das den CLR-Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="94a6e-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94a6e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94a6e-108">Remarks</span></span>  
 <span data-ttu-id="94a6e-109">Die `LoadModule` Rückruf stellt einen geeigneten Zeitpunkt zum Überprüfen der Metadaten für das Modul Just-in-Time (JIT)-Compilerflags festgelegt oder aktivieren oder Deaktivieren von Rückrufen für das Modul beim Laden.</span><span class="sxs-lookup"><span data-stu-id="94a6e-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94a6e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94a6e-110">Requirements</span></span>  
 <span data-ttu-id="94a6e-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94a6e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94a6e-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94a6e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94a6e-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94a6e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94a6e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94a6e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a6e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94a6e-115">See Also</span></span>  
 [<span data-ttu-id="94a6e-116">UnloadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="94a6e-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)  
 [<span data-ttu-id="94a6e-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94a6e-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
