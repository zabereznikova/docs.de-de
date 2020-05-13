---
title: ICorDebugManagedCallback::UnloadAssembly-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: 07996a78d7f559de587c8a3eb2babfc06675169d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212645"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="8a1ad-102">ICorDebugManagedCallback::UnloadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="8a1ad-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="8a1ad-103">Benachrichtigt den Debugger, dass eine Common Language Runtime Assembly entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="8a1ad-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a1ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a1ad-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a1ad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a1ad-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="8a1ad-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Assembly enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="8a1ad-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="8a1ad-107">in Ein Zeiger auf ein ICorDebug-Objekt, das die Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="8a1ad-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a1ad-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a1ad-108">Remarks</span></span>  
 <span data-ttu-id="8a1ad-109">Die Assembly sollte nach diesem Rückruf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a1ad-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a1ad-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8a1ad-110">Requirements</span></span>  
 <span data-ttu-id="8a1ad-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a1ad-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a1ad-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a1ad-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a1ad-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a1ad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a1ad-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a1ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a1ad-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a1ad-115">See also</span></span>

- [<span data-ttu-id="8a1ad-116">LoadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="8a1ad-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="8a1ad-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a1ad-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
