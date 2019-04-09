---
title: ICorDebugManagedCallback::CreateThread-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c48e92c73347957d8acc5c209f6f5473e9e18524
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223250"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="584c1-102">ICorDebugManagedCallback::CreateThread-Methode</span><span class="sxs-lookup"><span data-stu-id="584c1-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="584c1-103">Benachrichtigt den Debugger an, dass ein Thread die Ausführung von verwaltetem Code gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="584c1-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="584c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="584c1-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="584c1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="584c1-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="584c1-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="584c1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="584c1-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="584c1-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="584c1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="584c1-108">Remarks</span></span>  
 <span data-ttu-id="584c1-109">Der Thread wird positioniert werden, an der ersten Anweisung für verwalteten Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="584c1-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="584c1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="584c1-110">Requirements</span></span>  
 <span data-ttu-id="584c1-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="584c1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="584c1-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="584c1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="584c1-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="584c1-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="584c1-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="584c1-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="584c1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="584c1-115">See also</span></span>

- [<span data-ttu-id="584c1-116">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="584c1-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
