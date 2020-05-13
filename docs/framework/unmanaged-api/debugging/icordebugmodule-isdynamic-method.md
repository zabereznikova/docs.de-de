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
ms.openlocfilehash: 4517f266bbb500223214a6a8fe5881e8b29566c3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206883"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="a0516-102">ICorDebugModule::IsDynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="a0516-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="a0516-103">Ruft einen Wert ab, der angibt, ob dieses Modul dynamisch ist.</span><span class="sxs-lookup"><span data-stu-id="a0516-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0516-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0516-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0516-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0516-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="a0516-106">[out] `true` , wenn dieses Modul dynamisch ist. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="a0516-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0516-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0516-107">Remarks</span></span>  
 <span data-ttu-id="a0516-108">Ein dynamisches Modul kann neue Klassen hinzufügen und vorhandene Klassen löschen, auch nachdem das Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a0516-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="a0516-109">Die [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) -und [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) -Rückrufe benachrichtigen den Debugger, wenn eine Klasse hinzugefügt oder gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="a0516-109">The [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0516-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a0516-110">Requirements</span></span>  
 <span data-ttu-id="a0516-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0516-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0516-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0516-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0516-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0516-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0516-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0516-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
