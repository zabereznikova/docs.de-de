---
title: ICorDebugManagedCallback::UnloadAssembly-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e770602858761dbcf15c233dceebfd35be106aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214130"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="0ac13-102">ICorDebugManagedCallback::UnloadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="0ac13-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="0ac13-103">Benachrichtigt den Debugger, dass eine common Language Runtime-Assembly entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="0ac13-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ac13-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ac13-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ac13-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0ac13-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="0ac13-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="0ac13-107">[in] Ein Zeiger auf ein ICorDebugAssembly-Objekt, das die Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="0ac13-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ac13-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ac13-108">Remarks</span></span>  
 <span data-ttu-id="0ac13-109">Die Assembly sollte nach dieser Rückruf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ac13-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ac13-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ac13-110">Requirements</span></span>  
 <span data-ttu-id="0ac13-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ac13-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ac13-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ac13-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ac13-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ac13-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0ac13-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="0ac13-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ac13-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ac13-115">See also</span></span>

- [<span data-ttu-id="0ac13-116">LoadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="0ac13-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="0ac13-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ac13-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
