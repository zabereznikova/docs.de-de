---
title: ICorDebugValueEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
ms.openlocfilehash: ba61df045caa117acae3756eb879cf67d0791222
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791063"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="21e28-102">ICorDebugValueEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21e28-102">ICorDebugValueEnum Interface</span></span>
<span data-ttu-id="21e28-103">Implementiert die ICorDebugEnum-Methoden und listet die ICorDebugValue-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="21e28-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21e28-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="21e28-104">Methods</span></span>  
  
|<span data-ttu-id="21e28-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="21e28-105">Method</span></span>|<span data-ttu-id="21e28-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21e28-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21e28-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="21e28-107">Next Method</span></span>](icordebugvalueenum-next-method.md)|<span data-ttu-id="21e28-108">Ruft die angegebene Anzahl von `ICorDebugValue` Instanzen aus der-Enumeration ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="21e28-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21e28-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21e28-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21e28-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="21e28-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21e28-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21e28-111">Requirements</span></span>  
 <span data-ttu-id="21e28-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21e28-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21e28-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21e28-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21e28-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21e28-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21e28-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21e28-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e28-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21e28-116">See also</span></span>

- [<span data-ttu-id="21e28-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="21e28-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
