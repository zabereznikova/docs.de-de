---
title: ICorDebugManagedCallback::UnloadModule-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
ms.openlocfilehash: 88ef9fd5a0aac19954a247d0215fe698ebe30d40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788336"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="ca836-102">ICorDebugManagedCallback::UnloadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="ca836-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="ca836-103">Benachrichtigt den Debugger, dass ein Common Language Runtime Modul (dll) entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ca836-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca836-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca836-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca836-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ca836-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ca836-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die das Modul enthielt.</span><span class="sxs-lookup"><span data-stu-id="ca836-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="ca836-107">in Ein Zeiger auf ein ICorDebug Module-Objekt, das das Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="ca836-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca836-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca836-108">Remarks</span></span>  
 <span data-ttu-id="ca836-109">Das Modul sollte nach diesem-Befehl nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ca836-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca836-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca836-110">Requirements</span></span>  
 <span data-ttu-id="ca836-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca836-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca836-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca836-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca836-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca836-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca836-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca836-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca836-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca836-115">See also</span></span>

- [<span data-ttu-id="ca836-116">LoadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="ca836-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="ca836-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca836-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
