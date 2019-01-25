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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 27e2f194d252baa2e2ca185d905c945d26a177a0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590090"
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="706af-102">COR_PRF_CODEGEN_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="706af-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="706af-103">Definiert die codeerstellungskennzeichen, die mit festgelegt werden, können die [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="706af-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="706af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="706af-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="706af-105">Member</span><span class="sxs-lookup"><span data-stu-id="706af-105">Members</span></span>  
  
|<span data-ttu-id="706af-106">Member</span><span class="sxs-lookup"><span data-stu-id="706af-106">Member</span></span>|<span data-ttu-id="706af-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="706af-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="706af-108">Keine Funktionen werden in dieser Funktion den Text als inlinespalten betrachtet.</span><span class="sxs-lookup"><span data-stu-id="706af-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="706af-109">Die Funktion selbst kann jedoch jetzt Inline an seine Aufrufer eingebettet sein.</span><span class="sxs-lookup"><span data-stu-id="706af-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="706af-110">Alle Optimierungen werden für den Text für diese Funktion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="706af-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="706af-111">Die Funktion selbst kann jedoch weiterhin jetzt Inline an seine Aufrufer eingebettet sein.</span><span class="sxs-lookup"><span data-stu-id="706af-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="706af-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="706af-112">Remarks</span></span>  
 <span data-ttu-id="706af-113">Die `COR_PRF_CODEGEN_FLAGS` Enumeration wird verwendet, durch die [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) Methode, um den Profiler zu steuern, die codegenerierung für die erneut JIT-kompilierten Funktion zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="706af-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="706af-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="706af-114">Requirements</span></span>  
 <span data-ttu-id="706af-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="706af-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="706af-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="706af-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="706af-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="706af-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="706af-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="706af-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="706af-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="706af-119">See also</span></span>
- [<span data-ttu-id="706af-120">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="706af-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
