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
ms.openlocfilehash: c18ed781d44c873b4cd1957bf0102a4ce0cccad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139221"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="ae699-102">ICorDebugModule::EnableClassLoadCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="ae699-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="ae699-103">Steuert, ob die Rückrufe [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) für dieses Modul aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ae699-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae699-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae699-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae699-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae699-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="ae699-106">in Legen Sie diesen Wert auf `true` fest, damit der Common Language Runtime (CLR) die Methoden `ICorDebugManagedCallback::LoadClass` und `ICorDebugManagedCallback::UnloadClass` aufruft, wenn die zugehörigen Ereignisse eintreten.</span><span class="sxs-lookup"><span data-stu-id="ae699-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="ae699-107">Der Standardwert ist `false` für nicht dynamische Module.</span><span class="sxs-lookup"><span data-stu-id="ae699-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="ae699-108">Der Wert ist für dynamische Module immer `true` und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ae699-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae699-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ae699-109">Remarks</span></span>  
 <span data-ttu-id="ae699-110">Die `ICorDebugManagedCallback::LoadClass`-und `ICorDebugManagedCallback::UnloadClass` Rückrufe sind immer für dynamische Module aktiviert und können nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="ae699-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae699-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ae699-111">Requirements</span></span>  
 <span data-ttu-id="ae699-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae699-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae699-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae699-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae699-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae699-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae699-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae699-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae699-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae699-116">See also</span></span>
