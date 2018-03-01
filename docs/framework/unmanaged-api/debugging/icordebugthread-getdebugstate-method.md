---
title: ICorDebugThread::GetDebugState-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7b9d310cdc088e4b2fc9c6850accc3576a6147ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="f0dad-102">ICorDebugThread::GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="f0dad-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="f0dad-103">Ruft den aktuellen Debugzustand dieses ICorDebugThread-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="f0dad-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0dad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0dad-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0dad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0dad-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="f0dad-106">[out] Ein Zeiger auf eine bitweise Kombination von Enumerationswerten CorDebugThreadState, die den aktuellen Debugzustand dieses Threads zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="f0dad-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0dad-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0dad-107">Remarks</span></span>  
 <span data-ttu-id="f0dad-108">Wenn der Prozess derzeit angehalten wird, `pState` den Debugzustand, die für diesen Thread vorhanden wäre, wäre der Prozess fortgesetzt werden, wird nicht den tatsächlichen aktuellen Status des Threads darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0dad-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0dad-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0dad-109">Requirements</span></span>  
 <span data-ttu-id="f0dad-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0dad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0dad-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0dad-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0dad-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0dad-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0dad-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0dad-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
