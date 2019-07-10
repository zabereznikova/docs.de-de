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
ms.openlocfilehash: 0baabbb736365b138d1754e68070207b4310bf57
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762462"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="e9cd8-102">ICorDebugThread::GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="e9cd8-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="e9cd8-103">Ruft den aktuellen Debugzustand dieses ICorDebugThread-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="e9cd8-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9cd8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9cd8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9cd8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9cd8-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="e9cd8-106">[out] Ein Zeiger auf eine bitweise Kombination der Werte der CorDebugThreadState-Enumeration, die den aktuellen Debugzustand dieses Threads beschreibt.</span><span class="sxs-lookup"><span data-stu-id="e9cd8-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9cd8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9cd8-107">Remarks</span></span>  
 <span data-ttu-id="e9cd8-108">Wenn der Prozess gerade beendet wird, `pState` den Debugzustand, der für diesen Thread vorhanden wäre, würde der Vorgang fortgesetzt werden, wird nicht den aktuellen Zustand dieses Threads darstellt.</span><span class="sxs-lookup"><span data-stu-id="e9cd8-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9cd8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9cd8-109">Requirements</span></span>  
 <span data-ttu-id="e9cd8-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9cd8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9cd8-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9cd8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9cd8-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9cd8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9cd8-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9cd8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
