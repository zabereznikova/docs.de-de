---
title: COR_PRF_TRANSITION_REASON-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
ms.openlocfilehash: e890c62a54654e86bb4a825613807efe142c8d5a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500740"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="4e633-102">COR_PRF_TRANSITION_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4e633-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="4e633-103">Zeigt den Grund für einen Übergang von verwaltetem zu nicht verwaltetem Code an oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="4e633-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e633-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e633-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="4e633-105">Member</span><span class="sxs-lookup"><span data-stu-id="4e633-105">Members</span></span>  
  
|<span data-ttu-id="4e633-106">Member</span><span class="sxs-lookup"><span data-stu-id="4e633-106">Member</span></span>|<span data-ttu-id="4e633-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e633-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="4e633-108">Der Übergang erfolgt aufgrund eines Aufrufes für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="4e633-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="4e633-109">Der Übergang ist auf eine Rückgabe einer Funktion zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="4e633-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e633-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4e633-110">Remarks</span></span>  
 <span data-ttu-id="4e633-111">Wenn ein Übergang stattfindet, empfängt der Profiler einen [ICorProfilerCallback:: ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) -oder [ICorProfilerCallback:: UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) -Rückruf, der einen Wert der- `COR_PRF_TRANSITION_REASON` Enumeration bereitstellt, um den Grund für den Übergang anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4e633-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e633-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4e633-112">Requirements</span></span>  
 <span data-ttu-id="4e633-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e633-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e633-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e633-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e633-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e633-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e633-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e633-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
