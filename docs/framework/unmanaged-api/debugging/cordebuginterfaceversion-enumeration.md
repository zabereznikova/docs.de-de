---
title: CorDebugInterfaceVersion-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
ms.openlocfilehash: 939400fcc40edd62532d459d6ed626dbdc4f41fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675307"
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="5b887-102">CorDebugInterfaceVersion-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5b887-102">CorDebugInterfaceVersion Enumeration</span></span>

<span data-ttu-id="5b887-103">Legt eine Schnittstelle fest, eine Version des .NET Frameworks oder eine Version des .NET Frameworks, in dem eine Schnittstelle eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5b887-103">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b887-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b887-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a><span data-ttu-id="5b887-105">Member</span><span class="sxs-lookup"><span data-stu-id="5b887-105">Members</span></span>  

 <span data-ttu-id="5b887-106">Die folgende Tabelle enthält Links von jedem Enumerationswert zur entsprechenden Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5b887-106">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="5b887-107">Außerdem zeigt die Tabelle die erste .NET Framework Version, in der die Schnittstelle unterstützt wurde.</span><span class="sxs-lookup"><span data-stu-id="5b887-107">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="5b887-108">Member</span><span class="sxs-lookup"><span data-stu-id="5b887-108">Member</span></span>|<span data-ttu-id="5b887-109">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="5b887-109">Specifies</span></span>|<span data-ttu-id="5b887-110">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="5b887-110">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="5b887-111">Die Version von .NET Framework ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="5b887-111">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="5b887-112">Die Version von .NET Frameworks einschließlich sämtlicher Service Packs ist 1.0.</span><span class="sxs-lookup"><span data-stu-id="5b887-112">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="5b887-113">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-113">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="5b887-114">Die Version von .NET Frameworks einschließlich sämtlicher Service Packs ist 1.1.</span><span class="sxs-lookup"><span data-stu-id="5b887-114">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="5b887-115">1.1</span><span class="sxs-lookup"><span data-stu-id="5b887-115">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="5b887-116">Die Version von .NET Frameworks einschließlich sämtlicher Service Packs ist 2.0.</span><span class="sxs-lookup"><span data-stu-id="5b887-116">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="5b887-117">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-117">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="5b887-118">Die Version von .NET Frameworks einschließlich sämtlicher Service Packs ist 4.</span><span class="sxs-lookup"><span data-stu-id="5b887-118">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="5b887-119">4</span><span class="sxs-lookup"><span data-stu-id="5b887-119">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="5b887-120">Die Version von .NET Frameworks einschließlich sämtlicher Service Packs ist 4.5.</span><span class="sxs-lookup"><span data-stu-id="5b887-120">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="5b887-121">4,5</span><span class="sxs-lookup"><span data-stu-id="5b887-121">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="5b887-122">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5b887-122">ICorDebugManagedCallback</span></span>](icordebugmanagedcallback-interface.md)|<span data-ttu-id="5b887-123">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-123">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="5b887-124">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="5b887-124">ICorDebugUnmanagedCallback</span></span>](icordebugunmanagedcallback-interface.md)|<span data-ttu-id="5b887-125">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-125">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="5b887-126">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="5b887-126">ICorDebug</span></span>](icordebug-interface.md)|<span data-ttu-id="5b887-127">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-127">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="5b887-128">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="5b887-128">ICorDebugController</span></span>](icordebugcontroller-interface.md)|<span data-ttu-id="5b887-129">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-129">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="5b887-130">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="5b887-130">ICorDebugAppDomain</span></span>](icordebugappdomain-interface.md)|<span data-ttu-id="5b887-131">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-131">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="5b887-132">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="5b887-132">ICorDebugAssembly</span></span>](icordebugassembly-interface.md)|<span data-ttu-id="5b887-133">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-133">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="5b887-134">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="5b887-134">ICorDebugProcess</span></span>](icordebugprocess-interface.md)|<span data-ttu-id="5b887-135">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-135">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="5b887-136">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5b887-136">ICorDebugBreakpoint</span></span>](icordebugbreakpoint-interface.md)|<span data-ttu-id="5b887-137">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-137">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="5b887-138">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5b887-138">ICorDebugFunctionBreakpoint</span></span>](icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="5b887-139">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-139">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="5b887-140">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5b887-140">ICorDebugModuleBreakpoint</span></span>](icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="5b887-141">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-141">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="5b887-142">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5b887-142">ICorDebugValueBreakpoint</span></span>](icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="5b887-143">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-143">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="5b887-144">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="5b887-144">ICorDebugStepper</span></span>](icordebugstepper-interface.md)|<span data-ttu-id="5b887-145">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-145">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="5b887-146">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="5b887-146">ICorDebugRegisterSet</span></span>](icordebugregisterset-interface.md)|<span data-ttu-id="5b887-147">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-147">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="5b887-148">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="5b887-148">ICorDebugThread</span></span>](icordebugthread-interface.md)|<span data-ttu-id="5b887-149">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-149">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="5b887-150">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="5b887-150">ICorDebugChain</span></span>](icordebugchain-interface.md)|<span data-ttu-id="5b887-151">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-151">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="5b887-152">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="5b887-152">ICorDebugFrame</span></span>](icordebugframe-interface.md)|<span data-ttu-id="5b887-153">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-153">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="5b887-154">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="5b887-154">ICorDebugILFrame</span></span>](icordebugilframe-interface.md)|<span data-ttu-id="5b887-155">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-155">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="5b887-156">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="5b887-156">ICorDebugNativeFrame</span></span>](icordebugnativeframe-interface.md)|<span data-ttu-id="5b887-157">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-157">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="5b887-158">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="5b887-158">ICorDebugModule</span></span>](icordebugmodule-interface.md)|<span data-ttu-id="5b887-159">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-159">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="5b887-160">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="5b887-160">ICorDebugFunction</span></span>](icordebugfunction-interface1.md)|<span data-ttu-id="5b887-161">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-161">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="5b887-162">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="5b887-162">ICorDebugCode</span></span>](icordebugcode-interface1.md)|<span data-ttu-id="5b887-163">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-163">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="5b887-164">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="5b887-164">ICorDebugClass</span></span>](icordebugclass-interface.md)|<span data-ttu-id="5b887-165">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-165">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="5b887-166">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="5b887-166">ICorDebugEval</span></span>](icordebugeval-interface.md)|<span data-ttu-id="5b887-167">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-167">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="5b887-168">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="5b887-168">ICorDebugValue</span></span>](icordebugvalue-interface.md)|<span data-ttu-id="5b887-169">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-169">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="5b887-170">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="5b887-170">ICorDebugGenericValue</span></span>](icordebuggenericvalue-interface.md)|<span data-ttu-id="5b887-171">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-171">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="5b887-172">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="5b887-172">ICorDebugReferenceValue</span></span>](icordebugreferencevalue-interface.md)|<span data-ttu-id="5b887-173">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-173">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="5b887-174">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="5b887-174">ICorDebugHeapValue</span></span>](icordebugheapvalue-interface.md)|<span data-ttu-id="5b887-175">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-175">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="5b887-176">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="5b887-176">ICorDebugObjectValue</span></span>](icordebugobjectvalue-interface.md)|<span data-ttu-id="5b887-177">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-177">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="5b887-178">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="5b887-178">ICorDebugBoxValue</span></span>](icordebugboxvalue-interface.md)|<span data-ttu-id="5b887-179">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-179">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="5b887-180">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="5b887-180">ICorDebugStringValue</span></span>](icordebugstringvalue-interface.md)|<span data-ttu-id="5b887-181">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-181">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="5b887-182">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="5b887-182">ICorDebugArrayValue</span></span>](icordebugarrayvalue-interface.md)|<span data-ttu-id="5b887-183">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-183">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="5b887-184">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="5b887-184">ICorDebugContext</span></span>](icordebugcontext-interface.md)|<span data-ttu-id="5b887-185">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-185">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="5b887-186">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-186">ICorDebugEnum</span></span>](icordebugenum-interface1.md)|<span data-ttu-id="5b887-187">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-187">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="5b887-188">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-188">ICorDebugObjectEnum</span></span>](icordebugobjectenum-interface.md)|<span data-ttu-id="5b887-189">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-189">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="5b887-190">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-190">ICorDebugBreakpointEnum</span></span>](icordebugbreakpointenum-interface.md)|<span data-ttu-id="5b887-191">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-191">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="5b887-192">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-192">ICorDebugStepperEnum</span></span>](icordebugstepperenum-interface.md)|<span data-ttu-id="5b887-193">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-193">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="5b887-194">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-194">ICorDebugProcessEnum</span></span>](icordebugprocessenum-interface.md)|<span data-ttu-id="5b887-195">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-195">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="5b887-196">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-196">ICorDebugThreadEnum</span></span>](icordebugthreadenum-interface1.md)|<span data-ttu-id="5b887-197">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-197">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="5b887-198">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-198">ICorDebugFrameEnum</span></span>](icordebugframeenum-interface.md)|<span data-ttu-id="5b887-199">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-199">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="5b887-200">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-200">ICorDebugChainEnum</span></span>](icordebugchainenum-interface.md)|<span data-ttu-id="5b887-201">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-201">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="5b887-202">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-202">ICorDebugModuleEnum</span></span>](icordebugmoduleenum-interface.md)|<span data-ttu-id="5b887-203">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-203">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="5b887-204">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-204">ICorDebugValueEnum</span></span>](icordebugvalueenum-interface.md)|<span data-ttu-id="5b887-205">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-205">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="5b887-206">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-206">ICorDebugCodeEnum</span></span>](icordebugcodeenum-interface.md)|<span data-ttu-id="5b887-207">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-207">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="5b887-208">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-208">ICorDebugTypeEnum</span></span>](icordebugtypeenum-interface.md)|<span data-ttu-id="5b887-209">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-209">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="5b887-210">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-210">ICorDebugErrorInfoEnum</span></span>](icordebugerrorinfoenum-interface.md)|<span data-ttu-id="5b887-211">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-211">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="5b887-212">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-212">ICorDebugAppDomainEnum</span></span>](icordebugappdomainenum-interface.md)|<span data-ttu-id="5b887-213">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-213">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="5b887-214">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="5b887-214">ICorDebugAssemblyEnum</span></span>](icordebugassemblyenum-interface.md)|<span data-ttu-id="5b887-215">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-215">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="5b887-216">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="5b887-216">ICorDebugEditAndContinueErrorInfo</span></span>](icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="5b887-217">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-217">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="5b887-218">ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="5b887-218">ICorDebugEditAndContinueSnapshot</span></span>](icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="5b887-219">1.0</span><span class="sxs-lookup"><span data-stu-id="5b887-219">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="5b887-220">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="5b887-220">ICorDebugManagedCallback2</span></span>](icordebugmanagedcallback2-interface.md)|<span data-ttu-id="5b887-221">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-221">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="5b887-222">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="5b887-222">ICorDebugAppDomain2</span></span>](icordebugappdomain2-interface.md)|<span data-ttu-id="5b887-223">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-223">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="5b887-224">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="5b887-224">ICorDebugProcess2</span></span>](icordebugprocess2-interface1.md)|<span data-ttu-id="5b887-225">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-225">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="5b887-226">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="5b887-226">ICorDebugStepper2</span></span>](icordebugstepper2-interface1.md)|<span data-ttu-id="5b887-227">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-227">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="5b887-228">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="5b887-228">ICorDebugRegisterSet2</span></span>](icordebugregisterset2-interface.md)|<span data-ttu-id="5b887-229">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-229">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="5b887-230">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="5b887-230">ICorDebugThread2</span></span>](icordebugthread2-interface.md)|<span data-ttu-id="5b887-231">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-231">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="5b887-232">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="5b887-232">ICorDebugILFrame2</span></span>](icordebugilframe2-interface.md)|<span data-ttu-id="5b887-233">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-233">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="5b887-234">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="5b887-234">ICorDebugModule2</span></span>](icordebugmodule2-interface.md)|<span data-ttu-id="5b887-235">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-235">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="5b887-236">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="5b887-236">ICorDebugFunction2</span></span>](icordebugfunction2-interface.md)|<span data-ttu-id="5b887-237">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-237">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="5b887-238">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="5b887-238">ICorDebugCode2</span></span>](icordebugcode2-interface.md)|<span data-ttu-id="5b887-239">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-239">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="5b887-240">ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="5b887-240">"ICorDebugClass2"</span></span>|<span data-ttu-id="5b887-241">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-241">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="5b887-242">ICorDebugValue2</span><span class="sxs-lookup"><span data-stu-id="5b887-242">"ICorDebugValue2"</span></span>|<span data-ttu-id="5b887-243">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-243">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="5b887-244">"ICorDebugEval2".</span><span class="sxs-lookup"><span data-stu-id="5b887-244">The "ICorDebugEval2".</span></span>|<span data-ttu-id="5b887-245">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-245">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="5b887-246">ICorDebugObjectValue2</span><span class="sxs-lookup"><span data-stu-id="5b887-246">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="5b887-247">2.0</span><span class="sxs-lookup"><span data-stu-id="5b887-247">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="5b887-248">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="5b887-248">ICorDebugThread3</span></span>](icordebugthread3-interface.md)|<span data-ttu-id="5b887-249">4</span><span class="sxs-lookup"><span data-stu-id="5b887-249">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="5b887-250">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="5b887-250">ICorDebugThread4</span></span>](icordebugthread4-interface.md)|<span data-ttu-id="5b887-251">4</span><span class="sxs-lookup"><span data-stu-id="5b887-251">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="5b887-252">ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="5b887-252">ICorDebugStackWalk</span></span>](icordebugstackwalk-interface.md)|<span data-ttu-id="5b887-253">4</span><span class="sxs-lookup"><span data-stu-id="5b887-253">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="5b887-254">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="5b887-254">ICorDebugNativeFrame2</span></span>](icordebugnativeframe2-interface.md)|<span data-ttu-id="5b887-255">4</span><span class="sxs-lookup"><span data-stu-id="5b887-255">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="5b887-256">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="5b887-256">ICorDebugInternalFrame2</span></span>](icordebuginternalframe2-interface.md)|<span data-ttu-id="5b887-257">4</span><span class="sxs-lookup"><span data-stu-id="5b887-257">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="5b887-258">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="5b887-258">ICorDebugRuntimeUnwindableFrame</span></span>](icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="5b887-259">4</span><span class="sxs-lookup"><span data-stu-id="5b887-259">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="5b887-260">ICorDebugHeapValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b887-260">ICorDebugHeapValue3 Interface</span></span>](icordebugheapvalue3-interface.md)|<span data-ttu-id="5b887-261">4</span><span class="sxs-lookup"><span data-stu-id="5b887-261">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="5b887-262">ICorDebugBlockingObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b887-262">ICorDebugBlockingObjectEnum Interface</span></span>](icordebugblockingobjectenum-interface.md)|<span data-ttu-id="5b887-263">4</span><span class="sxs-lookup"><span data-stu-id="5b887-263">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="5b887-264">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="5b887-264">ICorDebugValue3</span></span>](icordebugvalue3-interface.md)|<span data-ttu-id="5b887-265">4</span><span class="sxs-lookup"><span data-stu-id="5b887-265">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="5b887-266">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="5b887-266">ICorDebugComObjectValue</span></span>](icordebugcomobjectvalue-interface.md)|<span data-ttu-id="5b887-267">4,5</span><span class="sxs-lookup"><span data-stu-id="5b887-267">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="5b887-268">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="5b887-268">ICorDebugAppDomain3</span></span>](icordebugappdomain3-interface.md)|<span data-ttu-id="5b887-269">4,5</span><span class="sxs-lookup"><span data-stu-id="5b887-269">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="5b887-270">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="5b887-270">ICorDebugCode3</span></span>](icordebugcode3-interface.md)|<span data-ttu-id="5b887-271">4,5</span><span class="sxs-lookup"><span data-stu-id="5b887-271">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="5b887-272">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="5b887-272">ICorDebugILFrame3</span></span>](icordebugilframe3-interface.md)|<span data-ttu-id="5b887-273">4,5</span><span class="sxs-lookup"><span data-stu-id="5b887-273">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="5b887-274">Die Version von .NET Frameworks einschließlich sämtlicher Service Packs ist die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="5b887-274">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="5b887-275">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b887-275">Remarks</span></span>  

 <span data-ttu-id="5b887-276">Ein Debugger kann die- `CorDebugInterfaceVersion` Enumeration in der Funktion " [deedebugginginterfakefromversion](../hosting/createdebugginginterfacefromversion-function.md) " verwenden, um die höchste Version der .NET Framework anzugeben, die der Debugger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b887-276">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="5b887-277">Schnittstellennamen</span><span class="sxs-lookup"><span data-stu-id="5b887-277">Interface Names</span></span>  

 <span data-ttu-id="5b887-278">Der Name, der am Ende der Schnittstellennamen in der Debugging-API enthalten ist (z. B. die "3" in `ICorDebugThread3`) legt die Version der Schnittstelle fest, nicht die des .NET Frameworks.</span><span class="sxs-lookup"><span data-stu-id="5b887-278">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="5b887-279">Alle Schnittstellennamen in der Debugging-API enthalten Versionsnummern; ausgenommen sind Schnittstellen, die im .NET Framework Version 1 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="5b887-279">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="5b887-280">Sämtliche Übereinstimmungen zwischen den Schnittstellenversionsnummern und .NET Framework-Versionsnummern sind zufällig.</span><span class="sxs-lookup"><span data-stu-id="5b887-280">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
- <span data-ttu-id="5b887-281">Schnittstellen, die mit der .NET Framework Version 1.0 eingeführt wurden, enthalten keine Zahlen, da es sich dabei implizit immer um die Version 1 handelt.</span><span class="sxs-lookup"><span data-stu-id="5b887-281">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
- <span data-ttu-id="5b887-282">Die .NET Framework Version 1.1 verwendet Schnittstellen der Version 1.0 und führt keine neuen Debugging-Schnittstellen ein.</span><span class="sxs-lookup"><span data-stu-id="5b887-282">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
- <span data-ttu-id="5b887-283">Die 14 mit der .NET-Framework Version 2.0 eingeführten Debugging-Schnittstellen sind eine logische Erweiterung ihrer Gegenstücke aus der Version 1 und enthalten die Versionsnummer "2" im Namen.</span><span class="sxs-lookup"><span data-stu-id="5b887-283">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
- <span data-ttu-id="5b887-284">Die .NET Framework-Versionen 3.0 und 3.5 verwenden die vorhandenen Schnittstellen des .NET Framework 2.0 und führen keine neuen Schnittstellen ein.</span><span class="sxs-lookup"><span data-stu-id="5b887-284">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
- <span data-ttu-id="5b887-285">Der .NET Framework 4 führt eine Mischung aus Schnittstellen Versionen ein.</span><span class="sxs-lookup"><span data-stu-id="5b887-285">The .NET Framework 4 introduces a mix of interface versions.</span></span> <span data-ttu-id="5b887-286">Zum Beispiel erscheinen sowohl `ICorDebugThread3` als auch `ICorDebugThread4` als die dritte und vierte Version der `ICorDebugThread`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5b887-286">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="5b887-287">Der .NET Framework 4 führt außerdem die erste Version der `ICorDebugStackWalk` -Schnittstelle und die zweite Version der- `ICorDebugNativeFrame` Schnittstelle ( `ICorDebugNativeFrame2` ) ein.</span><span class="sxs-lookup"><span data-stu-id="5b887-287">The .NET Framework 4 also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b887-288">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5b887-288">Requirements</span></span>  

 <span data-ttu-id="5b887-289">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b887-289">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b887-290">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b887-290">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b887-291">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b887-291">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b887-292">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b887-292">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b887-293">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b887-293">See also</span></span>

- [<span data-ttu-id="5b887-294">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="5b887-294">Debugging Enumerations</span></span>](debugging-enumerations.md)
