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
ms.openlocfilehash: 6de2cb7c1a1423c5bd38a6f2e5d01c39166ab119
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791321"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="3f5ad-102">ICorDebugThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f5ad-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="3f5ad-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugThread-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="3f5ad-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f5ad-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3f5ad-104">Methods</span></span>  
  
|<span data-ttu-id="3f5ad-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="3f5ad-105">Method</span></span>|<span data-ttu-id="3f5ad-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3f5ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f5ad-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="3f5ad-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="3f5ad-108">Ruft die angegebene Anzahl von `ICorDebugThread` Instanzen aus der-Enumeration ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="3f5ad-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f5ad-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f5ad-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f5ad-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3f5ad-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f5ad-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3f5ad-111">Requirements</span></span>  
 <span data-ttu-id="3f5ad-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f5ad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f5ad-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f5ad-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f5ad-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f5ad-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f5ad-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f5ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f5ad-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f5ad-116">See also</span></span>

- [<span data-ttu-id="3f5ad-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3f5ad-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
