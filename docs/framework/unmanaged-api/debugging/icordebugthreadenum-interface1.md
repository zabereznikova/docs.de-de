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
ms.openlocfilehash: 82a7689bb1848d89f5dee4482d8dc7685c9c5b5c
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378336"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="aa852-102">ICorDebugThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa852-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="aa852-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugThread-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="aa852-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa852-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="aa852-104">Methods</span></span>  
  
|<span data-ttu-id="aa852-105">Methode</span><span class="sxs-lookup"><span data-stu-id="aa852-105">Method</span></span>|<span data-ttu-id="aa852-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa852-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa852-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="aa852-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="aa852-108">Ruft die angegebene Anzahl von- `ICorDebugThread` Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="aa852-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa852-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa852-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa852-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="aa852-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa852-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aa852-111">Requirements</span></span>  
 <span data-ttu-id="aa852-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa852-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa852-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa852-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa852-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa852-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa852-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa852-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa852-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa852-116">See also</span></span>

- [<span data-ttu-id="aa852-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="aa852-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
