---
title: ICorDebugManagedCallback::CreateAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type:
- apiref
ms.openlocfilehash: 35ea69d32ee9b994cc0bf91339c798edcd472f44
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788425"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="46d9a-102">ICorDebugManagedCallback::CreateAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="46d9a-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="46d9a-103">Benachrichtigt den Debugger, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="46d9a-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46d9a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46d9a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46d9a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="46d9a-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="46d9a-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem die Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="46d9a-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="46d9a-107">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die erstellte Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="46d9a-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46d9a-108">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="46d9a-108">Requirements</span></span>  
 <span data-ttu-id="46d9a-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46d9a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46d9a-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46d9a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46d9a-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46d9a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46d9a-112">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46d9a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d9a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46d9a-113">See also</span></span>

- [<span data-ttu-id="46d9a-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46d9a-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
