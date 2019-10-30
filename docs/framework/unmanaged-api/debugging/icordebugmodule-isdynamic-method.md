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
ms.openlocfilehash: 5774b40178ce0d7c2ef5d063a37b9011fc2630df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127948"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="6d7ce-102">ICorDebugModule::IsDynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="6d7ce-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="6d7ce-103">Ruft einen Wert ab, der angibt, ob dieses Modul dynamisch ist.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d7ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d7ce-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d7ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d7ce-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="6d7ce-106">[out] `true`, wenn dieses Modul dynamisch ist. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d7ce-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d7ce-107">Remarks</span></span>  
 <span data-ttu-id="6d7ce-108">Ein dynamisches Modul kann neue Klassen hinzufügen und vorhandene Klassen löschen, auch nachdem das Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="6d7ce-109">Die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) -und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) -Rückrufe benachrichtigen den Debugger, wenn eine Klasse hinzugefügt oder gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d7ce-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d7ce-110">Requirements</span></span>  
 <span data-ttu-id="6d7ce-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d7ce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d7ce-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d7ce-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d7ce-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d7ce-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d7ce-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d7ce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
