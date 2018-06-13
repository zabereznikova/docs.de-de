---
title: ICorDebugModule::IsDynamic-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5157c62f2719a9d62608750cd122561807197494
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418293"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="4f786-102">ICorDebugModule::IsDynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="4f786-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="4f786-103">Ruft einen Wert, der angibt, ob dieses Modul dynamisch ist.</span><span class="sxs-lookup"><span data-stu-id="4f786-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f786-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f786-104">Syntax</span></span>  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f786-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f786-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="4f786-106">[out] `true` ist dieses Modul dynamisch ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="4f786-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f786-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f786-107">Remarks</span></span>  
 <span data-ttu-id="4f786-108">Ein dynamisches Modul kann neue Klassen hinzufügen und löschen vorhandene Klassen, selbst wenn das Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4f786-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="4f786-109">Die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) Rückrufe informieren Sie den Debugger, wenn eine Klasse hinzugefügt oder gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="4f786-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f786-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f786-110">Requirements</span></span>  
 <span data-ttu-id="4f786-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f786-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f786-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f786-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f786-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f786-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f786-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f786-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
