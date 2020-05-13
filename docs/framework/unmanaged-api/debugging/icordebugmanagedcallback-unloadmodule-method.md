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
ms.openlocfilehash: 4b44a16d143c1daea1ea6c36eb096ab9a937b272
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210042"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="4b76a-102">ICorDebugManagedCallback::UnloadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="4b76a-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="4b76a-103">Benachrichtigt den Debugger, dass ein Common Language Runtime Modul (dll) entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4b76a-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b76a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b76a-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b76a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b76a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4b76a-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die das Modul enthielt.</span><span class="sxs-lookup"><span data-stu-id="4b76a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="4b76a-107">in Ein Zeiger auf ein ICorDebug Module-Objekt, das das Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="4b76a-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b76a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b76a-108">Remarks</span></span>  
 <span data-ttu-id="4b76a-109">Das Modul sollte nach diesem-Befehl nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b76a-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b76a-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4b76a-110">Requirements</span></span>  
 <span data-ttu-id="4b76a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b76a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b76a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b76a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b76a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b76a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b76a-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b76a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b76a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b76a-115">See also</span></span>

- [<span data-ttu-id="4b76a-116">LoadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="4b76a-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="4b76a-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b76a-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
