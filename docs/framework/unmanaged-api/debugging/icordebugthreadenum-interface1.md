---
title: ICorDebugThreadEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b7e5b0a9f4166923a559eb3886aa0f9cabbcd72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962946"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="3573b-102">ICorDebugThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3573b-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="3573b-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugThread-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="3573b-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3573b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3573b-104">Methods</span></span>  
  
|<span data-ttu-id="3573b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3573b-105">Method</span></span>|<span data-ttu-id="3573b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3573b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3573b-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="3573b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="3573b-108">Ruft die angegebene Anzahl von `ICorDebugThread` -Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="3573b-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3573b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3573b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3573b-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3573b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3573b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3573b-111">Requirements</span></span>  
 <span data-ttu-id="3573b-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3573b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3573b-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="3573b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3573b-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3573b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3573b-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3573b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3573b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3573b-116">See also</span></span>

- [<span data-ttu-id="3573b-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3573b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
