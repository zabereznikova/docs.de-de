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
ms.openlocfilehash: 5debd09f3ca0b4562f62913f9530cc4fa6f9110b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728029"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="95faf-102">ICorDebugThread::GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="95faf-102">ICorDebugThread::GetHandle Method</span></span>

<span data-ttu-id="95faf-103">Ruft das aktuelle Handle für den aktiven Teil dieses ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="95faf-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95faf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95faf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95faf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="95faf-105">Parameters</span></span>  

 `phThreadHandle`  
 <span data-ttu-id="95faf-106">vorgenommen Ein Zeiger auf einen hThread, der das Handle des aktiven Teils dieses Threads ist.</span><span class="sxs-lookup"><span data-stu-id="95faf-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95faf-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95faf-107">Remarks</span></span>  

 <span data-ttu-id="95faf-108">Das Handle kann sich ändern, wenn der Prozess ausgeführt wird, und unterscheidet sich möglicherweise für verschiedene Teile des Threads.</span><span class="sxs-lookup"><span data-stu-id="95faf-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="95faf-109">Dieses Handle gehört der Debug-API an.</span><span class="sxs-lookup"><span data-stu-id="95faf-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="95faf-110">Der Debugger sollte ihn vor der Verwendung duplizieren.</span><span class="sxs-lookup"><span data-stu-id="95faf-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95faf-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="95faf-111">Requirements</span></span>  

 <span data-ttu-id="95faf-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95faf-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95faf-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95faf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95faf-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95faf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95faf-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95faf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
