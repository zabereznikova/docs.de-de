---
title: COR_PRF_CODEGEN_FLAGS-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6fc50330b31e8b0f8def24aaafbf3a4b7e365e98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="e9023-102">COR_PRF_CODEGEN_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e9023-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="e9023-103">Definiert die codeerstellungskennzeichen, die mit festgelegt werden, können die [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e9023-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9023-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9023-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="e9023-105">Member</span><span class="sxs-lookup"><span data-stu-id="e9023-105">Members</span></span>  
  
|<span data-ttu-id="e9023-106">Member</span><span class="sxs-lookup"><span data-stu-id="e9023-106">Member</span></span>|<span data-ttu-id="e9023-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9023-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="e9023-108">Keine Funktionen werden in diese Funktion Text als inlinespalten betrachtet.</span><span class="sxs-lookup"><span data-stu-id="e9023-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="e9023-109">Allerdings kann die Funktion selbst inline in seine Aufrufer sein.</span><span class="sxs-lookup"><span data-stu-id="e9023-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="e9023-110">Alle Optimierungen werden für diese Funktion Text deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e9023-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="e9023-111">Die Funktion selbst sind jedoch weiterhin in seine Aufrufer inline möglicherweise.</span><span class="sxs-lookup"><span data-stu-id="e9023-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9023-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9023-112">Remarks</span></span>  
 <span data-ttu-id="e9023-113">Die `COR_PRF_CODEGEN_FLAGS` Enumeration wird verwendet, durch die [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) Methode, um den Profiler zum Steuern der codegenerierung für die JIT-kompilierten Funktion zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e9023-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9023-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9023-114">Requirements</span></span>  
 <span data-ttu-id="e9023-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9023-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9023-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e9023-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e9023-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9023-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9023-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9023-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9023-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9023-119">See Also</span></span>  
 [<span data-ttu-id="e9023-120">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="e9023-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
