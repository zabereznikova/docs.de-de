---
title: ICorDebugManagedCallback::Break-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83524b24fd05969fa4f45fd742d1df955c441d44
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732387"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="84418-102">ICorDebugManagedCallback::Break-Methode</span><span class="sxs-lookup"><span data-stu-id="84418-102">ICorDebugManagedCallback::Break Method</span></span>
<span data-ttu-id="84418-103">Benachrichtigt den Debugger bei einer <xref:System.Reflection.Emit.OpCodes.Break> -Anweisung im Codestream ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="84418-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84418-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84418-104">Syntax</span></span>  
  
```  
HRESULT Break (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84418-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84418-105">Parameters</span></span>  
 `pAppDOmain`  
 <span data-ttu-id="84418-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die die Break-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="84418-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>  
  
 `thread`  
 <span data-ttu-id="84418-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der die Break-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="84418-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84418-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84418-108">Requirements</span></span>  
 <span data-ttu-id="84418-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84418-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84418-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84418-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84418-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84418-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84418-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84418-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84418-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84418-113">See also</span></span>
- [<span data-ttu-id="84418-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84418-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
