---
title: ICorDebugProcessEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum
helpviewer_keywords:
- ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type:
- apiref
ms.openlocfilehash: c11e286d8c33d6823127d9a6d5989064e2299bc4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792144"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="9d790-102">ICorDebugProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d790-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="9d790-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugProcess-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="9d790-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d790-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9d790-104">Methods</span></span>  
  
|<span data-ttu-id="9d790-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="9d790-105">Method</span></span>|<span data-ttu-id="9d790-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d790-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d790-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="9d790-107">Next Method</span></span>](icordebugprocessenum-next-method.md)|<span data-ttu-id="9d790-108">Ruft die angegebene Anzahl von `ICorDebugProcess` Instanzen aus der-Enumeration ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="9d790-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d790-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d790-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d790-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9d790-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d790-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d790-111">Requirements</span></span>  
 <span data-ttu-id="9d790-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d790-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d790-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d790-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d790-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d790-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d790-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d790-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d790-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d790-116">See also</span></span>

- [<span data-ttu-id="9d790-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9d790-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
