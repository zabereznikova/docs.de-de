---
title: ICorDebugBreakpointEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
ms.openlocfilehash: 97e06a2f20dcc2bb3815b98ba29ff230e37ff29d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730161"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="583ea-102">ICorDebugBreakpointEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="583ea-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="583ea-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugBreakpoint-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="583ea-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="583ea-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="583ea-104">Methods</span></span>  
  
|<span data-ttu-id="583ea-105">Methode</span><span class="sxs-lookup"><span data-stu-id="583ea-105">Method</span></span>|<span data-ttu-id="583ea-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="583ea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="583ea-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="583ea-107">Next Method</span></span>](icordebugbreakpointenum-next-method.md)|<span data-ttu-id="583ea-108">Ruft die angegebene Anzahl von- `ICorDebugBreakpoint` Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="583ea-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="583ea-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="583ea-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="583ea-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="583ea-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="583ea-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="583ea-111">Requirements</span></span>  

 <span data-ttu-id="583ea-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="583ea-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="583ea-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="583ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="583ea-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="583ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="583ea-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="583ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="583ea-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="583ea-116">See also</span></span>

- [<span data-ttu-id="583ea-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="583ea-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
