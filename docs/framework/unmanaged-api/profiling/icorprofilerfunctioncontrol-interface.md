---
title: ICorProfilerFunctionControl-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl
helpviewer_keywords: ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09a0a839c9cd69c7926c19cceffc56ee928f2f02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="b07ad-102">ICorProfilerFunctionControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b07ad-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="b07ad-103">Stellt Methoden bereit, die einem Codeprofiler ermöglichen, mit der CLR (Common Language Runtime) zu kommunizieren, um zu steuern, wie der JIT-Compiler Code generieren soll, wenn er eine bestimmte Methode neu kompiliert.</span><span class="sxs-lookup"><span data-stu-id="b07ad-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b07ad-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b07ad-104">Methods</span></span>  
  
|<span data-ttu-id="b07ad-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b07ad-105">Method</span></span>|<span data-ttu-id="b07ad-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b07ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b07ad-107">SetCodegenFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="b07ad-107">SetCodegenFlags Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="b07ad-108">Legt ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) Steuerelement codegenerierung für eine just-in-Time (JIT)-Enumeration kompiliert Funktion.</span><span class="sxs-lookup"><span data-stu-id="b07ad-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="b07ad-109">SetILFunctionBody-Methode</span><span class="sxs-lookup"><span data-stu-id="b07ad-109">SetILFunctionBody Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="b07ad-110">Ersetzt den CIL-Text (Common Intermediate Language) der Methode.</span><span class="sxs-lookup"><span data-stu-id="b07ad-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="b07ad-111">SetILInstrumentedCodeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="b07ad-111">SetILInstrumentedCodeMap Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="b07ad-112">Legt eine Code Map für die angegebene Funktion mithilfe der festgelegten Zuordnungseinträge der Common Intermediate Language (CIL) fest.</span><span class="sxs-lookup"><span data-stu-id="b07ad-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b07ad-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b07ad-113">Remarks</span></span>  
 <span data-ttu-id="b07ad-114">Die `ICorProfilerFunctionControl`-Schnittstelle stellt Methoden zum Steuern der Codegenerierung für eine einzelne neu kompilierte Funktion bereit.</span><span class="sxs-lookup"><span data-stu-id="b07ad-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="b07ad-115">Der Profiler Ruft eine Instanz dieser Schnittstelle durch den [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="b07ad-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="b07ad-116">Jede Instanz von `ICorProfilerFunctionControl` steuert alle Instanzen einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="b07ad-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b07ad-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b07ad-117">Requirements</span></span>  
 <span data-ttu-id="b07ad-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b07ad-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b07ad-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b07ad-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b07ad-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b07ad-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b07ad-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b07ad-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b07ad-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b07ad-122">See Also</span></span>  
 [<span data-ttu-id="b07ad-123">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b07ad-123">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="b07ad-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b07ad-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="b07ad-125">EnumJITedFunctions2-Methode</span><span class="sxs-lookup"><span data-stu-id="b07ad-125">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
