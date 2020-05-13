---
title: ICorDebugThread::GetHandle-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
ms.openlocfilehash: 16aafa439fc81c3606f98ca2ba860316ec46e0db
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379740"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="9841c-102">ICorDebugThread::GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="9841c-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="9841c-103">Ruft das aktuelle Handle für den aktiven Teil dieses ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="9841c-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9841c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9841c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9841c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9841c-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="9841c-106">vorgenommen Ein Zeiger auf einen hThread, der das Handle des aktiven Teils dieses Threads ist.</span><span class="sxs-lookup"><span data-stu-id="9841c-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9841c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9841c-107">Remarks</span></span>  
 <span data-ttu-id="9841c-108">Das Handle kann sich ändern, wenn der Prozess ausgeführt wird, und unterscheidet sich möglicherweise für verschiedene Teile des Threads.</span><span class="sxs-lookup"><span data-stu-id="9841c-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="9841c-109">Dieses Handle gehört der Debug-API an.</span><span class="sxs-lookup"><span data-stu-id="9841c-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="9841c-110">Der Debugger sollte ihn vor der Verwendung duplizieren.</span><span class="sxs-lookup"><span data-stu-id="9841c-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9841c-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9841c-111">Requirements</span></span>  
 <span data-ttu-id="9841c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9841c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9841c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9841c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9841c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9841c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9841c-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9841c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
