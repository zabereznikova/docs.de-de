---
title: ICorDebugManagedCallback::UnloadAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29400e5bda2a17c731cb33e67c0123cffc89c48b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="83798-102">ICorDebugManagedCallback::UnloadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="83798-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="83798-103">Benachrichtigt den Debugger, dass eine common Language Runtime-Assembly entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="83798-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83798-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83798-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83798-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="83798-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="83798-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die die Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="83798-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="83798-107">[in] Ein Zeiger auf ein ICorDebugAssembly-Objekt, das die Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="83798-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83798-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83798-108">Remarks</span></span>  
 <span data-ttu-id="83798-109">Die Assembly sollte nach diesem Rückruf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83798-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83798-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83798-110">Requirements</span></span>  
 <span data-ttu-id="83798-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83798-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83798-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83798-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83798-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83798-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83798-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83798-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83798-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83798-115">See Also</span></span>  
 [<span data-ttu-id="83798-116">LoadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="83798-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)  
 [<span data-ttu-id="83798-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83798-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
