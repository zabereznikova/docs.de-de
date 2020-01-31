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
ms.openlocfilehash: 06c08499298656c8314d72667d9dac88c8d11e6a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788344"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="26590-102">ICorDebugManagedCallback::UnloadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="26590-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="26590-103">Benachrichtigt den Debugger, dass eine Common Language Runtime Assembly entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="26590-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26590-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26590-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26590-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="26590-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="26590-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Assembly enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="26590-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="26590-107">in Ein Zeiger auf ein ICorDebug-Objekt, das die Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="26590-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26590-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26590-108">Remarks</span></span>  
 <span data-ttu-id="26590-109">Die Assembly sollte nach diesem Rückruf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="26590-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26590-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="26590-110">Requirements</span></span>  
 <span data-ttu-id="26590-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26590-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26590-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26590-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26590-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26590-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26590-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26590-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26590-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26590-115">See also</span></span>

- [<span data-ttu-id="26590-116">LoadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="26590-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="26590-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26590-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
