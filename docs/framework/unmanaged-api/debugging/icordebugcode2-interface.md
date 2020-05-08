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
ms.openlocfilehash: 39767ea2603018d088aaefc5da32879aaf49fee6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893484"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="57494-102">ICorDebugCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57494-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="57494-103">Stellt Methoden bereit, mit denen die Funktionen von "ICorDebugCode" erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="57494-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57494-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="57494-104">Methods</span></span>  
  
|<span data-ttu-id="57494-105">Methode</span><span class="sxs-lookup"><span data-stu-id="57494-105">Method</span></span>|<span data-ttu-id="57494-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57494-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57494-107">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="57494-107">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="57494-108">Ruft die Codeabschnitte ab, aus denen dieses Codeobjekt besteht.</span><span class="sxs-lookup"><span data-stu-id="57494-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="57494-109">GetCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="57494-109">GetCompilerFlags Method</span></span>](icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="57494-110">Ruft die Flags ab, die die Bedingungen angeben, unter denen dieses Codeobjekt JIT-kompiliert (Just-In-Time) oder unter Verwendung des Native Image Generator (Ngen.exe) generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="57494-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57494-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57494-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57494-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="57494-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57494-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57494-113">Requirements</span></span>  
 <span data-ttu-id="57494-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57494-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57494-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57494-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57494-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57494-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57494-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57494-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57494-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57494-118">See also</span></span>

- [<span data-ttu-id="57494-119">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57494-119">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="57494-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="57494-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
