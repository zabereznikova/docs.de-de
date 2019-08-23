---
title: ICorDebugCode4-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ec40de7fe9e12315987e65e48f1727f5d5b80ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960730"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="f60a3-102">ICorDebugCode4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f60a3-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="f60a3-103">Stellt eine Methode bereit, die einem Debugger das Auflisten der lokalen Variablen und Argumente in einer Funktion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f60a3-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f60a3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f60a3-104">Methods</span></span>  
  
|<span data-ttu-id="f60a3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f60a3-105">Method</span></span>|<span data-ttu-id="f60a3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f60a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f60a3-107">EnumerateVariableHomes-Methode</span><span class="sxs-lookup"><span data-stu-id="f60a3-107">EnumerateVariableHomes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="f60a3-108">Ruft einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="f60a3-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f60a3-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f60a3-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f60a3-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f60a3-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f60a3-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f60a3-111">Requirements</span></span>  
 <span data-ttu-id="f60a3-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f60a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f60a3-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f60a3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f60a3-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f60a3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f60a3-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f60a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60a3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f60a3-116">See also</span></span>

- [<span data-ttu-id="f60a3-117">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f60a3-117">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="f60a3-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f60a3-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
