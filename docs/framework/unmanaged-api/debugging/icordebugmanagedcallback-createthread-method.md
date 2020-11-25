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
ms.openlocfilehash: 56ec7c56b167c29c9951638c5eee159e1d3c7ffb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721295"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="39c08-102">ICorDebugManagedCallback::CreateThread-Methode</span><span class="sxs-lookup"><span data-stu-id="39c08-102">ICorDebugManagedCallback::CreateThread Method</span></span>

<span data-ttu-id="39c08-103">Benachrichtigt den Debugger, dass ein Thread mit der Ausführung von verwaltetem Code begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="39c08-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39c08-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39c08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="39c08-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="39c08-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="39c08-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="39c08-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="39c08-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39c08-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39c08-108">Remarks</span></span>  

 <span data-ttu-id="39c08-109">Der Thread wird an der ersten Anweisung des verwalteten Codes positioniert, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="39c08-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39c08-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="39c08-110">Requirements</span></span>  

 <span data-ttu-id="39c08-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39c08-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39c08-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39c08-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39c08-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39c08-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39c08-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39c08-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c08-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39c08-115">See also</span></span>

- [<span data-ttu-id="39c08-116">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39c08-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
