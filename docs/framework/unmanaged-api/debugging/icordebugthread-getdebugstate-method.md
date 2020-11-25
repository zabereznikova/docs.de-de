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
ms.openlocfilehash: 746fef3629e6573d7dfe47d5a3fcf9ee9a1d4250
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728042"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="e1d18-102">ICorDebugThread::GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="e1d18-102">ICorDebugThread::GetDebugState Method</span></span>

<span data-ttu-id="e1d18-103">Ruft den aktuellen Debugzustand dieses ICorDebugThread-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="e1d18-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1d18-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1d18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1d18-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e1d18-105">Parameters</span></span>  

 `pState`  
 <span data-ttu-id="e1d18-106">vorgenommen Ein Zeiger auf eine bitweise Kombination von CorDebugThreadState-Enumerationswerten, die den aktuellen Debugzustand dieses Threads beschreibt.</span><span class="sxs-lookup"><span data-stu-id="e1d18-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1d18-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1d18-107">Remarks</span></span>  

 <span data-ttu-id="e1d18-108">Wenn der Prozess aktuell beendet ist, `pState` stellt den Debugzustand dar, der für diesen Thread vorhanden wäre, wenn der Prozess fortgesetzt werden soll, und nicht den tatsächlichen aktuellen Zustand dieses Threads.</span><span class="sxs-lookup"><span data-stu-id="e1d18-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1d18-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e1d18-109">Requirements</span></span>  

 <span data-ttu-id="e1d18-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1d18-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1d18-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1d18-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1d18-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1d18-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1d18-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1d18-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
