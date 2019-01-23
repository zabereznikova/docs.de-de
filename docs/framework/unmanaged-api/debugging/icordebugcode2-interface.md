---
title: ICorDebugCode2-Schnittstelle1
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
ms.openlocfilehash: 8a5c28ec6c447f3fc3305e0faf51aa868d5a4c17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499972"
---
# <a name="icordebugcode2-interface1"></a><span data-ttu-id="cda2e-102">ICorDebugCode2-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="cda2e-102">ICorDebugCode2 Interface1</span></span>
<span data-ttu-id="cda2e-103">Enthält Methoden, die die Funktionen "ICorDebugCode" erweitern.</span><span class="sxs-lookup"><span data-stu-id="cda2e-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cda2e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cda2e-104">Methods</span></span>  
  
|<span data-ttu-id="cda2e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="cda2e-105">Method</span></span>|<span data-ttu-id="cda2e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cda2e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cda2e-107">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="cda2e-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="cda2e-108">Ruft die Codeabschnitte ab, aus denen dieses Codeobjekt besteht.</span><span class="sxs-lookup"><span data-stu-id="cda2e-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="cda2e-109">GetCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="cda2e-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="cda2e-110">Ruft die Flags ab, die die Bedingungen angeben, unter denen dieses Codeobjekt JIT-kompiliert (Just-In-Time) oder unter Verwendung des Native Image Generator (Ngen.exe) generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="cda2e-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cda2e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cda2e-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cda2e-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cda2e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cda2e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cda2e-113">Requirements</span></span>  
 <span data-ttu-id="cda2e-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cda2e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cda2e-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cda2e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cda2e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cda2e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cda2e-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cda2e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda2e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cda2e-118">See also</span></span>

- [<span data-ttu-id="cda2e-119">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cda2e-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="cda2e-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cda2e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
