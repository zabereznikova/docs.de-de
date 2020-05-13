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
ms.openlocfilehash: 89fba6af9b76f729ca40d4ee63f525611bdf43a9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205637"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="3cc8e-102">ICorDebugManagedCallback::CreateAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="3cc8e-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="3cc8e-103">Benachrichtigt den Debugger, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3cc8e-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc8e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3cc8e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cc8e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3cc8e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="3cc8e-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem die Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3cc8e-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="3cc8e-107">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die erstellte Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="3cc8e-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cc8e-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3cc8e-108">Requirements</span></span>  
 <span data-ttu-id="3cc8e-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cc8e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cc8e-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cc8e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cc8e-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cc8e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cc8e-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cc8e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cc8e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cc8e-113">See also</span></span>

- [<span data-ttu-id="3cc8e-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3cc8e-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
