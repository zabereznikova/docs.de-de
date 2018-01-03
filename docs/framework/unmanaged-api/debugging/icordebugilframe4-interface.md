---
title: ICorDebugILFrame4-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame4
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66e4ba870319a1c60419ab794088a41eb9c4db3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="529bc-102">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="529bc-102">ICorDebugILFrame4 Interface</span></span>
<span data-ttu-id="529bc-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="529bc-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="529bc-104">Bietet Methoden, mit denen Sie auf lokale Variablen und Code in einem Stapelrahmen aus Intermediate Language (IL)-Code zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="529bc-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="529bc-105">Ein Parameter legt fest, ob der Debugger Zugang zu Variablen und Code erhält, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="529bc-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="529bc-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="529bc-106">Methods</span></span>  
  
|<span data-ttu-id="529bc-107">Methode</span><span class="sxs-lookup"><span data-stu-id="529bc-107">Method</span></span>|<span data-ttu-id="529bc-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="529bc-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="529bc-109">EnumerateLocalVariablesEx-Methode</span><span class="sxs-lookup"><span data-stu-id="529bc-109">EnumerateLocalVariablesEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="529bc-110">Gibt eine Liste der lokalen Variablen zurück, die im aktuellen Rahmen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="529bc-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="529bc-111">GetCodeEx-Methode</span><span class="sxs-lookup"><span data-stu-id="529bc-111">GetCodeEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="529bc-112">Gibt den Code zurück, den dieser Stapelrahmen ausführt.</span><span class="sxs-lookup"><span data-stu-id="529bc-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="529bc-113">GetLocalVariableEx-Methode</span><span class="sxs-lookup"><span data-stu-id="529bc-113">GetLocalVariableEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="529bc-114">Gibt den Wert einer lokalen Variable im IL-Stapelrahmen zurück.</span><span class="sxs-lookup"><span data-stu-id="529bc-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="529bc-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="529bc-115">Remarks</span></span>  
 <span data-ttu-id="529bc-116">Diese Methoden bieten zusätzlich zu den von bereitgestellte Funktionalität der [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), und [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) Methoden.</span><span class="sxs-lookup"><span data-stu-id="529bc-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), and [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="529bc-117">Jede Methode enthält einen `flags`-Parameter, der angibt, ob zusätzliche, durch eine ReJIT-Anfrage eines Profilers definierte, lokale Variablen oder Code sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="529bc-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="529bc-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="529bc-118">Requirements</span></span>  
 <span data-ttu-id="529bc-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="529bc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="529bc-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="529bc-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="529bc-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="529bc-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="529bc-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="529bc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="529bc-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="529bc-123">See Also</span></span>  
 [<span data-ttu-id="529bc-124">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="529bc-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="529bc-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="529bc-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
