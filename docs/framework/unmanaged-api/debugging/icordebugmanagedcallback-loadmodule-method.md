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
ms.openlocfilehash: cfca06c656f3274f4c5ddb06373a0296dc5e6905
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164540"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="b6454-102">ICorDebugManagedCallback::LoadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="b6454-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="b6454-103">Benachrichtigt den Debugger, dass ein common Language Runtime (CLR)-Modul wurde erfolgreich geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="b6454-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6454-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6454-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6454-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6454-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b6454-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der das Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="b6454-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="b6454-107">[in] Ein Zeiger auf ein ICorDebugModule-Objekt, das CLR-Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="b6454-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6454-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6454-108">Remarks</span></span>  
 <span data-ttu-id="b6454-109">Die `LoadModule` Rückruf stellt einen geeigneten Zeitpunkt zum Überprüfen der Metadaten für das Modul, Festlegen von just-in-Time (JIT) Compilerflags aktivieren oder Deaktivieren von Rückrufen für das Modul beim Laden.</span><span class="sxs-lookup"><span data-stu-id="b6454-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6454-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6454-110">Requirements</span></span>  
 <span data-ttu-id="b6454-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6454-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6454-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6454-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6454-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6454-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b6454-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b6454-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b6454-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6454-115">See also</span></span>

- [<span data-ttu-id="b6454-116">UnloadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="b6454-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="b6454-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6454-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
