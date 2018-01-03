---
title: ICorDebugThread::GetHandle-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7a932d04fef438e19176af565c92e0673339e02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="68a5b-102">ICorDebugThread::GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="68a5b-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="68a5b-103">Ruft das aktuelle Handle für den aktiven Teil des ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="68a5b-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68a5b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68a5b-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68a5b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="68a5b-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="68a5b-106">[out] Ein Zeiger auf einen HTHREAD, der das Handle des aktiven Teils dieses Threads ist.</span><span class="sxs-lookup"><span data-stu-id="68a5b-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68a5b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68a5b-107">Remarks</span></span>  
 <span data-ttu-id="68a5b-108">Das Handle kann sich ändern, wie der Prozess ausgeführt wird, und für die verschiedenen Teile des Threads kann abweichen.</span><span class="sxs-lookup"><span data-stu-id="68a5b-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="68a5b-109">Dieses Handle ist im Besitz der Debuggen-API.</span><span class="sxs-lookup"><span data-stu-id="68a5b-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="68a5b-110">Der Debugger sollte es duplizieren, bevor Sie ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="68a5b-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68a5b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68a5b-111">Requirements</span></span>  
 <span data-ttu-id="68a5b-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68a5b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68a5b-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68a5b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68a5b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68a5b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68a5b-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68a5b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
