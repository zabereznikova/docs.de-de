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
ms.openlocfilehash: d552b694787b5d9f0d5adc399eda6f75df93c385
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793027"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="5c27c-102">ICorDebugModule::EnableClassLoadCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="5c27c-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="5c27c-103">Steuert, ob die Rückrufe [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) für dieses Modul aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5c27c-103">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c27c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c27c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c27c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5c27c-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="5c27c-106">in Legen Sie diesen Wert auf `true` fest, damit der Common Language Runtime (CLR) die Methoden `ICorDebugManagedCallback::LoadClass` und `ICorDebugManagedCallback::UnloadClass` aufruft, wenn die zugehörigen Ereignisse eintreten.</span><span class="sxs-lookup"><span data-stu-id="5c27c-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="5c27c-107">Der Standardwert ist `false` für nicht dynamische Module.</span><span class="sxs-lookup"><span data-stu-id="5c27c-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="5c27c-108">Der Wert ist für dynamische Module immer `true` und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5c27c-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c27c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c27c-109">Remarks</span></span>  
 <span data-ttu-id="5c27c-110">Die `ICorDebugManagedCallback::LoadClass`-und `ICorDebugManagedCallback::UnloadClass` Rückrufe sind immer für dynamische Module aktiviert und können nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5c27c-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c27c-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c27c-111">Requirements</span></span>  
 <span data-ttu-id="5c27c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c27c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c27c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c27c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c27c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c27c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c27c-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c27c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c27c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c27c-116">See also</span></span>
