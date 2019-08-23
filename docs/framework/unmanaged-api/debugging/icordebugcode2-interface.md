---
title: ICorDebugCode2-Schnittstelle
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
ms.openlocfilehash: 9cb7be64089a55e7b653fcd6272219abba311af8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960799"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="f1e02-102">ICorDebugCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1e02-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="f1e02-103">Stellt Methoden bereit, mit denen die Funktionen von "ICorDebugCode" erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="f1e02-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1e02-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f1e02-104">Methods</span></span>  
  
|<span data-ttu-id="f1e02-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f1e02-105">Method</span></span>|<span data-ttu-id="f1e02-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1e02-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1e02-107">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="f1e02-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="f1e02-108">Ruft die Codeabschnitte ab, aus denen dieses Codeobjekt besteht.</span><span class="sxs-lookup"><span data-stu-id="f1e02-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="f1e02-109">GetCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="f1e02-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="f1e02-110">Ruft die Flags ab, die die Bedingungen angeben, unter denen dieses Codeobjekt JIT-kompiliert (Just-In-Time) oder unter Verwendung des Native Image Generator (Ngen.exe) generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f1e02-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1e02-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1e02-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1e02-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f1e02-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1e02-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1e02-113">Requirements</span></span>  
 <span data-ttu-id="f1e02-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1e02-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1e02-115">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f1e02-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1e02-116">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1e02-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1e02-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1e02-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e02-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1e02-118">See also</span></span>

- [<span data-ttu-id="f1e02-119">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1e02-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="f1e02-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f1e02-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
