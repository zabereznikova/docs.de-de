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
ms.openlocfilehash: 4ae4856eca2c1441ea53df0d9ed3648700b39b24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130659"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="586ef-102">ICorDebugManagedCallback::UnloadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="586ef-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="586ef-103">Benachrichtigt den Debugger, dass eine Common Language Runtime Assembly entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="586ef-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="586ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="586ef-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="586ef-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="586ef-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="586ef-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Assembly enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="586ef-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="586ef-107">in Ein Zeiger auf ein ICorDebug-Objekt, das die Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="586ef-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="586ef-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="586ef-108">Remarks</span></span>  
 <span data-ttu-id="586ef-109">Die Assembly sollte nach diesem Rückruf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="586ef-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="586ef-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="586ef-110">Requirements</span></span>  
 <span data-ttu-id="586ef-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="586ef-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="586ef-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="586ef-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="586ef-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="586ef-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="586ef-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="586ef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="586ef-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="586ef-115">See also</span></span>

- [<span data-ttu-id="586ef-116">LoadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="586ef-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="586ef-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="586ef-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
