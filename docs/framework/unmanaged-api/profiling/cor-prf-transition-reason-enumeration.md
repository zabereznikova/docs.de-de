---
title: COR_PRF_TRANSITION_REASON-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_TRANSITION_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_TRANSITION_REASON
helpviewer_keywords: COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9f11b5fb5409ee30b0456e0c562545718ed46bb6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="e49da-102">COR_PRF_TRANSITION_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e49da-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="e49da-103">Zeigt den Grund für einen Übergang von verwaltetem zu nicht verwaltetem Code an oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="e49da-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e49da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e49da-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="e49da-105">Member</span><span class="sxs-lookup"><span data-stu-id="e49da-105">Members</span></span>  
  
|<span data-ttu-id="e49da-106">Member</span><span class="sxs-lookup"><span data-stu-id="e49da-106">Member</span></span>|<span data-ttu-id="e49da-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e49da-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="e49da-108">Der Übergang ist aufgrund eines Aufrufs an eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="e49da-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="e49da-109">Der Übergang ist aufgrund einer Rückgabe von einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="e49da-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e49da-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e49da-110">Remarks</span></span>  
 <span data-ttu-id="e49da-111">Wenn ein Übergang erfolgt, empfängt der Profiler eine [ICorProfilerCallback:: ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) oder [ICorProfilerCallback:: UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) Rückruf, der die Stellt einen Wert von der `COR_PRF_TRANSITION_REASON` Enumeration, um den Grund für den Übergang anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e49da-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e49da-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e49da-112">Requirements</span></span>  
 <span data-ttu-id="e49da-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e49da-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e49da-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e49da-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e49da-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e49da-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e49da-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e49da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
