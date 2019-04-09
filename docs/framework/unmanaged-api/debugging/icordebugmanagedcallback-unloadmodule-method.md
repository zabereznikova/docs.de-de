---
title: ICorDebugManagedCallback::UnloadModule-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12e42da015864e83663d2f4d74bab2a34052d760
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083543"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="7395c-102">ICorDebugManagedCallback::UnloadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="7395c-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="7395c-103">Benachrichtigt den Debugger, dass ein common Language Runtime-Modul (DLL) entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7395c-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7395c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7395c-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7395c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7395c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7395c-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="7395c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="7395c-107">[in] Ein Zeiger auf ein ICorDebugModule-Objekt, das das Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="7395c-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7395c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7395c-108">Remarks</span></span>  
 <span data-ttu-id="7395c-109">Das Modul sollte nach dem Aufruf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7395c-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7395c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7395c-110">Requirements</span></span>  
 <span data-ttu-id="7395c-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7395c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7395c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7395c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7395c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7395c-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7395c-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7395c-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7395c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7395c-115">See also</span></span>

- [<span data-ttu-id="7395c-116">LoadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="7395c-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="7395c-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7395c-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
