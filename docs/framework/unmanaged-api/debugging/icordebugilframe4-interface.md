---
title: ICorDebugILFrame4-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
ms.openlocfilehash: 7f1c5d7a6fdae3e4c5a66c9aa4a82911105f4597
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788502"
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="1a9d7-102">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a9d7-102">ICorDebugILFrame4 Interface</span></span>
<span data-ttu-id="1a9d7-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="1a9d7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1a9d7-104">Bietet Methoden, mit denen Sie auf lokale Variablen und Code in einem Stapelrahmen aus Intermediate Language (IL)-Code zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1a9d7-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="1a9d7-105">Ein Parameter legt fest, ob der Debugger Zugang zu Variablen und Code erhält, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="1a9d7-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a9d7-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="1a9d7-106">Methods</span></span>  
  
|<span data-ttu-id="1a9d7-107">-Methode</span><span class="sxs-lookup"><span data-stu-id="1a9d7-107">Method</span></span>|<span data-ttu-id="1a9d7-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a9d7-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a9d7-109">EnumerateLocalVariablesEx-Methode</span><span class="sxs-lookup"><span data-stu-id="1a9d7-109">EnumerateLocalVariablesEx Method</span></span>](icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="1a9d7-110">Gibt eine Liste der lokalen Variablen zurück, die im aktuellen Rahmen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1a9d7-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="1a9d7-111">GetCodeEx-Methode</span><span class="sxs-lookup"><span data-stu-id="1a9d7-111">GetCodeEx Method</span></span>](icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="1a9d7-112">Gibt den Code zurück, den dieser Stapelrahmen ausführt.</span><span class="sxs-lookup"><span data-stu-id="1a9d7-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="1a9d7-113">GetLocalVariableEx-Methode</span><span class="sxs-lookup"><span data-stu-id="1a9d7-113">GetLocalVariableEx Method</span></span>](icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="1a9d7-114">Gibt den Wert einer lokalen Variable im IL-Stapelrahmen zurück.</span><span class="sxs-lookup"><span data-stu-id="1a9d7-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a9d7-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a9d7-115">Remarks</span></span>  
 <span data-ttu-id="1a9d7-116">Diese Methoden bieten zusätzlich zu den Funktionen, die von den Methoden [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md), [GetCode](icordebugframe-getcode-method.md)und [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1a9d7-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md), [GetCode](icordebugframe-getcode-method.md), and [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="1a9d7-117">Jede Methode enthält einen `flags`-Parameter, der angibt, ob zusätzliche, durch eine ReJIT-Anfrage eines Profilers definierte, lokale Variablen oder Code sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="1a9d7-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a9d7-118">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1a9d7-118">Requirements</span></span>  
 <span data-ttu-id="1a9d7-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a9d7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a9d7-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a9d7-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a9d7-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a9d7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a9d7-122">**.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a9d7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a9d7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a9d7-123">See also</span></span>

- [<span data-ttu-id="1a9d7-124">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1a9d7-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1a9d7-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1a9d7-125">Debugging</span></span>](index.md)
