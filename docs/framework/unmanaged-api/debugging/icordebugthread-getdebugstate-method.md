---
title: ICorDebugThread::GetDebugState-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68df19120f2e0b45e73f9d5e137afc8a5e7ac513
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489890"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="bb264-102">ICorDebugThread::GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="bb264-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="bb264-103">Ruft den aktuellen Debugzustand dieses ICorDebugThread-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="bb264-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb264-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb264-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb264-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb264-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="bb264-106">[out] Ein Zeiger auf eine bitweise Kombination der Werte der CorDebugThreadState-Enumeration, die den aktuellen Debugzustand dieses Threads beschreibt.</span><span class="sxs-lookup"><span data-stu-id="bb264-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb264-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb264-107">Remarks</span></span>  
 <span data-ttu-id="bb264-108">Wenn der Prozess gerade beendet wird, `pState` den Debugzustand, der für diesen Thread vorhanden wäre, würde der Vorgang fortgesetzt werden, wird nicht den aktuellen Zustand dieses Threads darstellt.</span><span class="sxs-lookup"><span data-stu-id="bb264-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb264-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb264-109">Requirements</span></span>  
 <span data-ttu-id="bb264-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb264-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb264-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb264-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb264-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb264-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb264-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb264-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
