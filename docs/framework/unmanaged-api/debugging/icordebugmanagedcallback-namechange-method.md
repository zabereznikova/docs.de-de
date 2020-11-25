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
ms.openlocfilehash: 0307ad5794d641833c2da1a1674e455ebff24861
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726521"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="61db5-102">ICorDebugManagedCallback::NameChange-Methode</span><span class="sxs-lookup"><span data-stu-id="61db5-102">ICorDebugManagedCallback::NameChange Method</span></span>

<span data-ttu-id="61db5-103">Benachrichtigt den Debugger, dass sich der Name einer Anwendungsdomäne oder eines Threads geändert hat.</span><span class="sxs-lookup"><span data-stu-id="61db5-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61db5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61db5-104">Syntax</span></span>  
  
```cpp  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61db5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61db5-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="61db5-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die entweder eine Namensänderung aufweist oder den Thread mit einer Namensänderung enthält.</span><span class="sxs-lookup"><span data-stu-id="61db5-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="61db5-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der eine Namensänderung aufweist.</span><span class="sxs-lookup"><span data-stu-id="61db5-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61db5-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="61db5-108">Requirements</span></span>  

 <span data-ttu-id="61db5-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61db5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61db5-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61db5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61db5-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61db5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61db5-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61db5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61db5-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61db5-113">See also</span></span>

- [<span data-ttu-id="61db5-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61db5-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
