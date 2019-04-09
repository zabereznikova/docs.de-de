---
title: ICorDebugCodeEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f36ce2fbf57c72102550069989c94b5cc19e58c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186653"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="27802-102">ICorDebugCodeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27802-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="27802-103">Implementiert "ICorDebugEnum"-Methoden und listet "ICorDebugType"-Arrays.</span><span class="sxs-lookup"><span data-stu-id="27802-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27802-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="27802-104">Methods</span></span>  
  
|<span data-ttu-id="27802-105">Methode</span><span class="sxs-lookup"><span data-stu-id="27802-105">Method</span></span>|<span data-ttu-id="27802-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27802-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27802-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="27802-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="27802-108">Ruft die angegebene Anzahl von `ICorDebugCode` Instanzen aus der Enumeration, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="27802-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27802-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27802-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27802-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="27802-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27802-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27802-111">Requirements</span></span>  
 <span data-ttu-id="27802-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27802-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27802-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27802-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27802-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27802-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="27802-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="27802-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="27802-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27802-116">See also</span></span>

- [<span data-ttu-id="27802-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="27802-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
