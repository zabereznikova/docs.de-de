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
ms.openlocfilehash: 373df8a47bdcbc833ffaea05bb205a63b5f583ec
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777770"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="a9a89-102">ICorDebugCode4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9a89-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="a9a89-103">Stellt eine Methode bereit, die einem Debugger das Auflisten der lokalen Variablen und Argumente in einer Funktion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a9a89-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9a89-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a9a89-104">Methods</span></span>  
  
|<span data-ttu-id="a9a89-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="a9a89-105">Method</span></span>|<span data-ttu-id="a9a89-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9a89-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9a89-107">EnumerateVariableHomes-Methode</span><span class="sxs-lookup"><span data-stu-id="a9a89-107">EnumerateVariableHomes Method</span></span>](icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="a9a89-108">Ruft einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="a9a89-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9a89-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9a89-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9a89-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a9a89-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9a89-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a9a89-111">Requirements</span></span>  
 <span data-ttu-id="a9a89-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9a89-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9a89-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9a89-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9a89-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9a89-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9a89-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9a89-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a89-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9a89-116">See also</span></span>

- [<span data-ttu-id="a9a89-117">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9a89-117">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="a9a89-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a9a89-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
