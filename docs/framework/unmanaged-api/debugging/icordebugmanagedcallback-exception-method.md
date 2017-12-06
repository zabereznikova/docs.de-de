---
title: ICorDebugManagedCallback::Exception-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.Exception
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 550b4961cb082ca6ee745b1d998a6fa95a22ace3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="a2345-102">ICorDebugManagedCallback::Exception-Methode</span><span class="sxs-lookup"><span data-stu-id="a2345-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="a2345-103">Benachrichtigt den Debugger, dass eine Ausnahme in verwaltetem Code ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="a2345-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2345-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2345-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2345-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2345-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a2345-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="a2345-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="a2345-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="a2345-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="a2345-108">[in] Wenn dieser Wert ist `false`, die Ausnahme ist noch nicht wurde von der Anwendung verarbeitet wird; andernfalls, die Ausnahme nicht behandelt wird und den Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="a2345-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2345-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2345-109">Remarks</span></span>  
 <span data-ttu-id="a2345-110">Die spezifische Ausnahme kann aus dem Threadobjekt abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a2345-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2345-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2345-111">Requirements</span></span>  
 <span data-ttu-id="a2345-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2345-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2345-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2345-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2345-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2345-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2345-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2345-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2345-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2345-116">See Also</span></span>  
 [<span data-ttu-id="a2345-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2345-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
