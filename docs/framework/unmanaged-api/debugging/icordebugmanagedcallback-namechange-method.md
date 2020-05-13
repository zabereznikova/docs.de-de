---
title: ICorDebugManagedCallback::NameChange-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
ms.openlocfilehash: 48bfce9966ff12fe1b425fbcd9a81860628a54e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212671"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="bb952-102">ICorDebugManagedCallback::NameChange-Methode</span><span class="sxs-lookup"><span data-stu-id="bb952-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="bb952-103">Benachrichtigt den Debugger, dass sich der Name einer Anwendungsdomäne oder eines Threads geändert hat.</span><span class="sxs-lookup"><span data-stu-id="bb952-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb952-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb952-104">Syntax</span></span>  
  
```cpp  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb952-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb952-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="bb952-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die entweder eine Namensänderung aufweist oder den Thread mit einer Namensänderung enthält.</span><span class="sxs-lookup"><span data-stu-id="bb952-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="bb952-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der eine Namensänderung aufweist.</span><span class="sxs-lookup"><span data-stu-id="bb952-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb952-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bb952-108">Requirements</span></span>  
 <span data-ttu-id="bb952-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb952-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb952-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb952-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb952-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb952-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb952-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb952-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb952-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb952-113">See also</span></span>

- [<span data-ttu-id="bb952-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb952-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
