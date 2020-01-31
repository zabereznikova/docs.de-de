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
ms.openlocfilehash: 4dd4e39c9092d018f13e3bd2822e9492d71141ad
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867294"
---
# <a name="cor_prf_codegen_flags-enumeration"></a><span data-ttu-id="28ef1-102">COR_PRF_CODEGEN_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="28ef1-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="28ef1-103">Definiert die Codegenerierungs-Flags, die mit der [icorprofilerfunctioncontrol:: setcodegenflags](icorprofilerfunctioncontrol-setcodegenflags-method.md) -Methode festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="28ef1-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ef1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28ef1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="28ef1-105">Member</span><span class="sxs-lookup"><span data-stu-id="28ef1-105">Members</span></span>  
  
|<span data-ttu-id="28ef1-106">Member</span><span class="sxs-lookup"><span data-stu-id="28ef1-106">Member</span></span>|<span data-ttu-id="28ef1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28ef1-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="28ef1-108">Keine Funktionen werden in den Text dieser Funktion eingebettet.</span><span class="sxs-lookup"><span data-stu-id="28ef1-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="28ef1-109">Die Funktion selbst kann jedoch in ihre Aufrufer eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="28ef1-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="28ef1-110">Alle Optimierungen werden für den Text dieser Funktion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="28ef1-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="28ef1-111">Die Funktion selbst kann jedoch weiterhin in ihren Aufrufern eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="28ef1-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28ef1-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28ef1-112">Remarks</span></span>  
 <span data-ttu-id="28ef1-113">Die `COR_PRF_CODEGEN_FLAGS`-Enumeration wird von der [icorprofilerfunctioncontrol:: setcodegenflags](icorprofilerfunctioncontrol-setcodegenflags-method.md) -Methode verwendet, um dem Profiler zu ermöglichen, die Codegenerierung für die JIT-neu kompilierte Funktion zu steuern.</span><span class="sxs-lookup"><span data-stu-id="28ef1-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28ef1-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28ef1-114">Requirements</span></span>  
 <span data-ttu-id="28ef1-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28ef1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28ef1-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28ef1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28ef1-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28ef1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28ef1-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28ef1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ef1-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28ef1-119">See also</span></span>

- [<span data-ttu-id="28ef1-120">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="28ef1-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
