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
ms.openlocfilehash: ca7668f23671721477c561774bab03279c4c18c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678557"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="c688b-102">ICorDebugThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c688b-102">ICorDebugThreadEnum Interface</span></span>

<span data-ttu-id="c688b-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugThread-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="c688b-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c688b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c688b-104">Methods</span></span>  
  
|<span data-ttu-id="c688b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c688b-105">Method</span></span>|<span data-ttu-id="c688b-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c688b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c688b-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="c688b-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="c688b-108">Ruft die angegebene Anzahl von- `ICorDebugThread` Instanzen ab der aktuellen Position aus der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="c688b-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c688b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c688b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c688b-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c688b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c688b-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c688b-111">Requirements</span></span>  

 <span data-ttu-id="c688b-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c688b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c688b-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c688b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c688b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c688b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c688b-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c688b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c688b-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c688b-116">See also</span></span>

- [<span data-ttu-id="c688b-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c688b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
