---
title: ICorDebugModule::EnableClassLoadCallbacks-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
ms.openlocfilehash: 1ca3adf30ad633fcfb10a4b43a435698d2899597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213529"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="c56dd-102">ICorDebugModule::EnableClassLoadCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="c56dd-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="c56dd-103">Steuert, ob die Rückrufe [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) für dieses Modul aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c56dd-103">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c56dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c56dd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c56dd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c56dd-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="c56dd-106">in Legen Sie diesen Wert auf fest, `true` damit der Common Language Runtime (CLR) die `ICorDebugManagedCallback::LoadClass` -Methode und die-Methode aufruft, `ICorDebugManagedCallback::UnloadClass` Wenn die zugehörigen Ereignisse eintreten.</span><span class="sxs-lookup"><span data-stu-id="c56dd-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="c56dd-107">Der Standardwert ist `false` für nicht dynamische Module.</span><span class="sxs-lookup"><span data-stu-id="c56dd-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="c56dd-108">Der Wert ist immer `true` für dynamische Module und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c56dd-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c56dd-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c56dd-109">Remarks</span></span>  
 <span data-ttu-id="c56dd-110">Die `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` Rückrufe und sind für dynamische Module immer aktiviert und können nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c56dd-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c56dd-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c56dd-111">Requirements</span></span>  
 <span data-ttu-id="c56dd-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c56dd-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c56dd-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c56dd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c56dd-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c56dd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c56dd-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c56dd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c56dd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c56dd-116">See also</span></span>
