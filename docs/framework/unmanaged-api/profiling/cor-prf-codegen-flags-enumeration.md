---
title: COR_PRF_CODEGEN_FLAGS-Enumeration
ms.date: 03/30/2017
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
ms.openlocfilehash: c49bdcb9345960bce018cefd4443948f997c7267
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428362"
---
# <a name="cor_prf_codegen_flags-enumeration"></a><span data-ttu-id="17f57-102">COR_PRF_CODEGEN_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="17f57-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="17f57-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="17f57-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17f57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17f57-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="17f57-105">Member</span><span class="sxs-lookup"><span data-stu-id="17f57-105">Members</span></span>  
  
|<span data-ttu-id="17f57-106">Member</span><span class="sxs-lookup"><span data-stu-id="17f57-106">Member</span></span>|<span data-ttu-id="17f57-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17f57-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="17f57-108">No functions will be inlined into this function’s body.</span><span class="sxs-lookup"><span data-stu-id="17f57-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="17f57-109">However, the function itself may be inlined into its callers.</span><span class="sxs-lookup"><span data-stu-id="17f57-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="17f57-110">All optimizations will be disabled for this function’s body.</span><span class="sxs-lookup"><span data-stu-id="17f57-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="17f57-111">However, the function itself may still be inlined into its callers.</span><span class="sxs-lookup"><span data-stu-id="17f57-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17f57-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17f57-112">Remarks</span></span>  
 <span data-ttu-id="17f57-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span><span class="sxs-lookup"><span data-stu-id="17f57-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17f57-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17f57-114">Requirements</span></span>  
 <span data-ttu-id="17f57-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17f57-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17f57-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="17f57-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="17f57-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17f57-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17f57-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17f57-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f57-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17f57-119">See also</span></span>

- [<span data-ttu-id="17f57-120">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="17f57-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
