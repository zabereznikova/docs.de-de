---
title: ICorDebugManagedCallback::ExitAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aed6ccd938761385aafd21802829bd741847b4ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110239"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="98240-102">ICorDebugManagedCallback::ExitAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="98240-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="98240-103">Benachrichtigt den Debugger, dass eine Anwendungsdomäne beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="98240-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98240-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98240-104">Syntax</span></span>  
  
```  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98240-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="98240-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="98240-106">[in] Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, der zur angegebenen Anwendungsdomäne enthält.</span><span class="sxs-lookup"><span data-stu-id="98240-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="98240-107">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="98240-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98240-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="98240-108">Requirements</span></span>  
 <span data-ttu-id="98240-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98240-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98240-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98240-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98240-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98240-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98240-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98240-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98240-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98240-113">See also</span></span>

- [<span data-ttu-id="98240-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98240-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
