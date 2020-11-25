---
title: ICorDebugModuleEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
ms.openlocfilehash: 08d16393a04888cd3f1a03fa209a1fceac28520b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724753"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="7ff12-102">ICorDebugModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ff12-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="7ff12-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugModule-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="7ff12-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ff12-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7ff12-104">Methods</span></span>  
  
|<span data-ttu-id="7ff12-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7ff12-105">Method</span></span>|<span data-ttu-id="7ff12-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ff12-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ff12-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="7ff12-107">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="7ff12-108">Ruft die angegebene Anzahl von- `ICorDebugModule` Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="7ff12-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ff12-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ff12-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ff12-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7ff12-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ff12-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7ff12-111">Requirements</span></span>  

 <span data-ttu-id="7ff12-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ff12-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ff12-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ff12-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ff12-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ff12-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ff12-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ff12-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff12-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ff12-116">See also</span></span>

- [<span data-ttu-id="7ff12-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7ff12-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
