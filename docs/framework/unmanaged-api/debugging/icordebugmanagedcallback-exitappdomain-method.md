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
ms.openlocfilehash: 51beed47e7187d6fa22e60baed16598a8ad73adb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688990"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="b34d2-102">ICorDebugManagedCallback::ExitAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="b34d2-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>

<span data-ttu-id="b34d2-103">Benachrichtigt den Debugger, dass eine Anwendungsdomäne beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b34d2-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b34d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b34d2-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b34d2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b34d2-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="b34d2-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, der die angegebene Anwendungsdomäne enthält.</span><span class="sxs-lookup"><span data-stu-id="b34d2-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="b34d2-107">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b34d2-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b34d2-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b34d2-108">Requirements</span></span>  

 <span data-ttu-id="b34d2-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b34d2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b34d2-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b34d2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b34d2-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b34d2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b34d2-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b34d2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b34d2-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b34d2-113">See also</span></span>

- [<span data-ttu-id="b34d2-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b34d2-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
