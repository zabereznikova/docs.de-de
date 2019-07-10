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
ms.openlocfilehash: db5d07d2b9a295a5cd21b4d4af954503b8bd7a8b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763668"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="b0dba-102">ICorDebugModule::IsDynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="b0dba-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="b0dba-103">Ruft einen Wert, der angibt, ob dieses Modul dynamisch ist.</span><span class="sxs-lookup"><span data-stu-id="b0dba-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0dba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0dba-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0dba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b0dba-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="b0dba-106">[out] `true` Wenn dieses Modul, dynamische, andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="b0dba-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0dba-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0dba-107">Remarks</span></span>  
 <span data-ttu-id="b0dba-108">Ein dynamisches Modul kann neue Klassen hinzufügen und löschen vorhandene Klassen aus, auch wenn das Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0dba-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="b0dba-109">Die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) -Rückrufe informieren Sie den Debugger, wenn eine Klasse hinzugefügt oder gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="b0dba-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0dba-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0dba-110">Requirements</span></span>  
 <span data-ttu-id="b0dba-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0dba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0dba-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0dba-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0dba-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0dba-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0dba-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0dba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
