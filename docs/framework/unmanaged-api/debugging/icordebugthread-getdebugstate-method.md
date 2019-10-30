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
ms.openlocfilehash: f054f8f2bd7c322e722a1e17290ba6fbad9e37b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133507"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="d0b1b-102">ICorDebugThread::GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="d0b1b-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="d0b1b-103">Ruft den aktuellen Debugzustand dieses ICorDebugThread-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b1b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0b1b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0b1b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0b1b-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="d0b1b-106">vorgenommen Ein Zeiger auf eine bitweise Kombination von CorDebugThreadState-Enumerationswerten, die den aktuellen Debugzustand dieses Threads beschreibt.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0b1b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d0b1b-107">Remarks</span></span>  
 <span data-ttu-id="d0b1b-108">Wenn der Prozess derzeit beendet ist, stellt `pState` den Debugzustand dar, der für diesen Thread vorhanden wäre, wenn der Prozess fortgesetzt werden soll, nicht den tatsächlichen aktuellen Zustand dieses Threads.</span><span class="sxs-lookup"><span data-stu-id="d0b1b-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0b1b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0b1b-109">Requirements</span></span>  
 <span data-ttu-id="d0b1b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0b1b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0b1b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0b1b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0b1b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0b1b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0b1b-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b1b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
