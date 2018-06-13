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
ms.openlocfilehash: 95d9696e29bc1b460c94d7f4d8afd3de82653333
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419629"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="c556b-102">ICorDebugThread::GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="c556b-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="c556b-103">Ruft den aktuellen Debugzustand dieses ICorDebugThread-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="c556b-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c556b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c556b-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c556b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c556b-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="c556b-106">[out] Ein Zeiger auf eine bitweise Kombination von Enumerationswerten CorDebugThreadState, die den aktuellen Debugzustand dieses Threads zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="c556b-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c556b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c556b-107">Remarks</span></span>  
 <span data-ttu-id="c556b-108">Wenn der Prozess derzeit angehalten wird, `pState` den Debugzustand, die für diesen Thread vorhanden wäre, wäre der Prozess fortgesetzt werden, wird nicht den tatsächlichen aktuellen Status des Threads darstellt.</span><span class="sxs-lookup"><span data-stu-id="c556b-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c556b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c556b-109">Requirements</span></span>  
 <span data-ttu-id="c556b-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c556b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c556b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c556b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c556b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c556b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c556b-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c556b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
