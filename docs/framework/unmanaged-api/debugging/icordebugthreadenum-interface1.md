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
ms.openlocfilehash: 7edf103e397c6e3e1577b5ed4bc8fc0df264b843
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137994"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="2454a-102">ICorDebugThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2454a-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="2454a-103">ICorDebugEnum-Methoden implementiert, und listet ICorDebugThread-Arrays.</span><span class="sxs-lookup"><span data-stu-id="2454a-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2454a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2454a-104">Methods</span></span>  
  
|<span data-ttu-id="2454a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2454a-105">Method</span></span>|<span data-ttu-id="2454a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2454a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2454a-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="2454a-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="2454a-108">Ruft die angegebene Anzahl von `ICorDebugThread` Instanzen aus der Enumeration, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="2454a-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2454a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2454a-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2454a-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2454a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2454a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2454a-111">Requirements</span></span>  
 <span data-ttu-id="2454a-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2454a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2454a-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2454a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2454a-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2454a-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2454a-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2454a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2454a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2454a-116">See also</span></span>

- [<span data-ttu-id="2454a-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2454a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
