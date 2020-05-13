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
ms.openlocfilehash: 13125f60f596cb8a80d9c42c51a979f632de494b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379759"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="9ebce-102">ICorDebugThread::GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="9ebce-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="9ebce-103">Ruft den aktuellen Debugzustand dieses ICorDebugThread-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="9ebce-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ebce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ebce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ebce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ebce-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="9ebce-106">vorgenommen Ein Zeiger auf eine bitweise Kombination von CorDebugThreadState-Enumerationswerten, die den aktuellen Debugzustand dieses Threads beschreibt.</span><span class="sxs-lookup"><span data-stu-id="9ebce-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ebce-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ebce-107">Remarks</span></span>  
 <span data-ttu-id="9ebce-108">Wenn der Prozess aktuell beendet ist, `pState` stellt den Debugzustand dar, der für diesen Thread vorhanden wäre, wenn der Prozess fortgesetzt werden soll, und nicht den tatsächlichen aktuellen Zustand dieses Threads.</span><span class="sxs-lookup"><span data-stu-id="9ebce-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ebce-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9ebce-109">Requirements</span></span>  
 <span data-ttu-id="9ebce-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ebce-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ebce-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ebce-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ebce-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ebce-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ebce-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ebce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
