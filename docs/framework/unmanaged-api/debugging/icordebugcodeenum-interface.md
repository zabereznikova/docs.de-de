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
ms.openlocfilehash: 3a771100ad4d63173fdb3b1ddea5ae3d67fbbc7c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960676"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="fcc4d-102">ICorDebugCodeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcc4d-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="fcc4d-103">Implementiert die ICorDebugEnum-Methoden und listet die ICorDebugCode-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="fcc4d-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fcc4d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fcc4d-104">Methods</span></span>  
  
|<span data-ttu-id="fcc4d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fcc4d-105">Method</span></span>|<span data-ttu-id="fcc4d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcc4d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fcc4d-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="fcc4d-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="fcc4d-108">Ruft die angegebene Anzahl von `ICorDebugCode` -Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="fcc4d-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcc4d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcc4d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fcc4d-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fcc4d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcc4d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fcc4d-111">Requirements</span></span>  
 <span data-ttu-id="fcc4d-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcc4d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcc4d-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="fcc4d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcc4d-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcc4d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcc4d-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcc4d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc4d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcc4d-116">See also</span></span>

- [<span data-ttu-id="fcc4d-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fcc4d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
