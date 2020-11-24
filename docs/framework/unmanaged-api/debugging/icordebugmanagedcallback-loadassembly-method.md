---
title: ICorDebugManagedCallback::LoadAssembly-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
ms.openlocfilehash: 243a1661ce2910cf1713ef8884bb6ae5422e8013
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679688"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="142d4-102">ICorDebugManagedCallback::LoadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="142d4-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>

<span data-ttu-id="142d4-103">Benachrichtigt den Debugger, dass eine Common Language Runtime-Assembly (CLR) erfolgreich geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="142d4-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="142d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="142d4-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="142d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="142d4-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="142d4-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in die die Assembly geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="142d4-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="142d4-107">in Ein Zeiger auf ein ICorDebug-Objekt, das die Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="142d4-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="142d4-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="142d4-108">Requirements</span></span>  

 <span data-ttu-id="142d4-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="142d4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="142d4-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="142d4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="142d4-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="142d4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="142d4-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="142d4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142d4-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="142d4-113">See also</span></span>

- [<span data-ttu-id="142d4-114">UnloadAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="142d4-114">UnloadAssembly Method</span></span>](icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="142d4-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="142d4-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
