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
ms.openlocfilehash: 127022fb8e9f9559ccb0f0c877d25db67eea3037
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784011"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="e98fc-102">ICorDebugCodeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e98fc-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="e98fc-103">Implementiert die ICorDebugEnum-Methoden und listet die ICorDebugCode-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="e98fc-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e98fc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e98fc-104">Methods</span></span>  
  
|<span data-ttu-id="e98fc-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="e98fc-105">Method</span></span>|<span data-ttu-id="e98fc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e98fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e98fc-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="e98fc-107">Next Method</span></span>](icordebugcodeenum-next-method.md)|<span data-ttu-id="e98fc-108">Ruft die angegebene Anzahl von `ICorDebugCode` Instanzen aus der-Enumeration ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="e98fc-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e98fc-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e98fc-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e98fc-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e98fc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e98fc-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e98fc-111">Requirements</span></span>  
 <span data-ttu-id="e98fc-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e98fc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e98fc-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e98fc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e98fc-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e98fc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e98fc-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e98fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e98fc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e98fc-116">See also</span></span>

- [<span data-ttu-id="e98fc-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e98fc-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
