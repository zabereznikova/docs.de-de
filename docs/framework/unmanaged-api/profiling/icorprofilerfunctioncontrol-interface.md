---
title: ICorProfilerFunctionControl-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 1286ce953c96eb3e3164ba5b209031dd1ec5c453
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864699"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="beee3-102">ICorProfilerFunctionControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="beee3-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="beee3-103">Stellt Methoden bereit, die einem Codeprofiler ermöglichen, mit der CLR (Common Language Runtime) zu kommunizieren, um zu steuern, wie der JIT-Compiler Code generieren soll, wenn er eine bestimmte Methode neu kompiliert.</span><span class="sxs-lookup"><span data-stu-id="beee3-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="beee3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="beee3-104">Methods</span></span>  
  
|<span data-ttu-id="beee3-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="beee3-105">Method</span></span>|<span data-ttu-id="beee3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beee3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="beee3-107">SetCodegenFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="beee3-107">SetCodegenFlags Method</span></span>](icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="beee3-108">Legt ein oder mehrere Flags aus der [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) -Enumeration fest, um die Codegenerierung für die neu kompilierte Just-in-time (JIT)-Funktion zu steuern.</span><span class="sxs-lookup"><span data-stu-id="beee3-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="beee3-109">SetILFunctionBody-Methode</span><span class="sxs-lookup"><span data-stu-id="beee3-109">SetILFunctionBody Method</span></span>](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="beee3-110">Ersetzt den CIL-Text (Common Intermediate Language) der Methode.</span><span class="sxs-lookup"><span data-stu-id="beee3-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="beee3-111">SetILInstrumentedCodeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="beee3-111">SetILInstrumentedCodeMap Method</span></span>](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="beee3-112">Legt eine Codezuordnung für die angegebene Funktion mit den angegebenen Common Intermediate Language (CIL)-Zuordnungseinträgen fest.</span><span class="sxs-lookup"><span data-stu-id="beee3-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beee3-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="beee3-113">Remarks</span></span>  
 <span data-ttu-id="beee3-114">Die `ICorProfilerFunctionControl`-Schnittstelle stellt Methoden zum Steuern der Codegenerierung für eine einzelne neu kompilierte Funktion bereit.</span><span class="sxs-lookup"><span data-stu-id="beee3-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="beee3-115">Der Profiler Ruft eine Instanz dieser Schnittstelle über den [ICorProfilerCallback4:: getrejitparameters](icorprofilercallback4-getrejitparameters-method.md) -Rückruf ab.</span><span class="sxs-lookup"><span data-stu-id="beee3-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="beee3-116">Jede Instanz von `ICorProfilerFunctionControl` steuert alle Instanzen einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="beee3-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beee3-117">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="beee3-117">Requirements</span></span>  
 <span data-ttu-id="beee3-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beee3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beee3-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="beee3-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="beee3-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beee3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beee3-121">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beee3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beee3-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beee3-122">See also</span></span>

- [<span data-ttu-id="beee3-123">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="beee3-123">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="beee3-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="beee3-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="beee3-125">EnumJITedFunctions2-Methode</span><span class="sxs-lookup"><span data-stu-id="beee3-125">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)
