---
title: ICorDebugCode2 Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13803a8cc292da602b1b920a3879120c3e754ca4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414557"
---
# <a name="icordebugcode2-interface1"></a><span data-ttu-id="fd7f9-102">ICorDebugCode2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="fd7f9-102">ICorDebugCode2 Interface1</span></span>
<span data-ttu-id="fd7f9-103">Enthält Methoden, die die Funktionen "ICorDebugCode" erweitern.</span><span class="sxs-lookup"><span data-stu-id="fd7f9-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd7f9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fd7f9-104">Methods</span></span>  
  
|<span data-ttu-id="fd7f9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fd7f9-105">Method</span></span>|<span data-ttu-id="fd7f9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd7f9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd7f9-107">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="fd7f9-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="fd7f9-108">Ruft die Codeabschnitte ab, aus denen dieses Codeobjekt besteht.</span><span class="sxs-lookup"><span data-stu-id="fd7f9-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="fd7f9-109">GetCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="fd7f9-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="fd7f9-110">Ruft die Flags ab, die die Bedingungen angeben, unter denen dieses Codeobjekt JIT-kompiliert (Just-In-Time) oder unter Verwendung des Native Image Generator (Ngen.exe) generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fd7f9-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd7f9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd7f9-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd7f9-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fd7f9-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd7f9-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd7f9-113">Requirements</span></span>  
 <span data-ttu-id="fd7f9-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd7f9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd7f9-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd7f9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd7f9-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd7f9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd7f9-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd7f9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7f9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd7f9-118">See Also</span></span>  
    
 [<span data-ttu-id="fd7f9-119">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd7f9-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="fd7f9-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fd7f9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
