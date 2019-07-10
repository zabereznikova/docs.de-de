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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c22e3c7c04a2b85723f1c0dba4543465faccab58
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745493"
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="5071d-102">COR_PRF_TRANSITION_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5071d-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="5071d-103">Zeigt den Grund für einen Übergang von verwaltetem zu nicht verwaltetem Code an oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="5071d-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5071d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5071d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="5071d-105">Member</span><span class="sxs-lookup"><span data-stu-id="5071d-105">Members</span></span>  
  
|<span data-ttu-id="5071d-106">Member</span><span class="sxs-lookup"><span data-stu-id="5071d-106">Member</span></span>|<span data-ttu-id="5071d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5071d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="5071d-108">Der Übergang erfolgt aufgrund eines Aufrufs an eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="5071d-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="5071d-109">Der Übergang erfolgt aufgrund einer Rückgabe von einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="5071d-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5071d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5071d-110">Remarks</span></span>  
 <span data-ttu-id="5071d-111">Wenn ein Übergang erfolgt, empfängt der Profiler eine [ICorProfilerCallback:: ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) oder [ICorProfilerCallback:: UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) Rückruf, der die Stellt den Wert der `COR_PRF_TRANSITION_REASON` Enumeration, um den Grund für den Übergang anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5071d-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5071d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5071d-112">Requirements</span></span>  
 <span data-ttu-id="5071d-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5071d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5071d-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5071d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5071d-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5071d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5071d-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5071d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
