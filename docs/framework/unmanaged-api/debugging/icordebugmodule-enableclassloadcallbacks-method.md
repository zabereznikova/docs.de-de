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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5bb3ab2eafa3465dba82b5326f663635e2b3e64
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655217"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="25856-102">ICorDebugModule::EnableClassLoadCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="25856-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="25856-103">Steuerelemente, ob die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) Rückrufe für dieses Modul aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="25856-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25856-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25856-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25856-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="25856-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="25856-106">[in] Legen Sie diesen Wert auf `true` So aktivieren Sie die common Language Runtime (CLR) zum Aufrufen der `ICorDebugManagedCallback::LoadClass` und `ICorDebugManagedCallback::UnloadClass` Methoden ein, wenn die zugeordneten Ereignisse auftreten.</span><span class="sxs-lookup"><span data-stu-id="25856-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="25856-107">Der Standardwert ist `false` für nicht dynamische Module.</span><span class="sxs-lookup"><span data-stu-id="25856-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="25856-108">Der Wert ist immer `true` bei dynamischen Modulen kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="25856-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25856-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25856-109">Remarks</span></span>  
 <span data-ttu-id="25856-110">Die `ICorDebugManagedCallback::LoadClass` und `ICorDebugManagedCallback::UnloadClass` Rückrufe werden für dynamische Module immer aktiviert und kann nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="25856-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25856-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25856-111">Requirements</span></span>  
 <span data-ttu-id="25856-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25856-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25856-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25856-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25856-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25856-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25856-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25856-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25856-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25856-116">See also</span></span>


