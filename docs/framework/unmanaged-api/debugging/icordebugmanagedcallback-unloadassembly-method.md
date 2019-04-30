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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995097"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="4e260-102">ICorDebugManagedCallback::UnloadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="4e260-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="4e260-103">Benachrichtigt den Debugger, dass eine common Language Runtime-Assembly entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4e260-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e260-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e260-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e260-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e260-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4e260-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="4e260-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="4e260-107">[in] Ein Zeiger auf ein ICorDebugAssembly-Objekt, das die Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="4e260-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e260-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e260-108">Remarks</span></span>  
 <span data-ttu-id="4e260-109">Die Assembly sollte nach dieser Rückruf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e260-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e260-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e260-110">Requirements</span></span>  
 <span data-ttu-id="4e260-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e260-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e260-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e260-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e260-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e260-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e260-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e260-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e260-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e260-115">See also</span></span>

- [<span data-ttu-id="4e260-116">LoadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="4e260-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="4e260-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e260-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
