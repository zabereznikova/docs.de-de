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
ms.openlocfilehash: b019c198635373fa6aaea01914dc9747b7486ae0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792877"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="3ca06-102">ICorDebugModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ca06-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="3ca06-103">Implementiert ICorDebugEnum-Methoden und listet ICorDebugModule-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="3ca06-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ca06-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3ca06-104">Methods</span></span>  
  
|<span data-ttu-id="3ca06-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="3ca06-105">Method</span></span>|<span data-ttu-id="3ca06-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ca06-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ca06-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="3ca06-107">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="3ca06-108">Ruft die angegebene Anzahl von `ICorDebugModule` Instanzen aus der-Enumeration ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="3ca06-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ca06-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ca06-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ca06-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3ca06-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca06-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ca06-111">Requirements</span></span>  
 <span data-ttu-id="3ca06-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ca06-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca06-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ca06-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ca06-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ca06-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ca06-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ca06-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca06-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ca06-116">See also</span></span>

- [<span data-ttu-id="3ca06-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3ca06-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
