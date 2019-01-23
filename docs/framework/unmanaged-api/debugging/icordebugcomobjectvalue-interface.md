---
title: ICorDebugComObjectValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4db005e1de043e60ffe958de732a5280fcccbea7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529946"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="229f2-102">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="229f2-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="229f2-103">Stellt Methoden zum Abrufen von Informationen, die einen Runtime callable Wrapper (RCW) zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="229f2-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="229f2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="229f2-104">Methods</span></span>  
  
|<span data-ttu-id="229f2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="229f2-105">Method</span></span>|<span data-ttu-id="229f2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="229f2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="229f2-107">GetCachedInterfacePointers-Methode</span><span class="sxs-lookup"><span data-stu-id="229f2-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="229f2-108">Ruft den unformatierten Schnittstellenzeiger, der für den aktuellen RCW zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="229f2-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="229f2-109">GetCachedInterfaceTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="229f2-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="229f2-110">Stellt einen Enumerator für die Schnittstellentypen bereit, dass das aktuelle Objekt Groß-/Kleinschreibung beachtet oder als verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="229f2-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="229f2-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="229f2-111">Remarks</span></span>  
 <span data-ttu-id="229f2-112">Um zu überprüfen, ob eine Instanz einer Schnittstelle "ICorDebugValue" einen RCW darstellt, ein Debugger ruft `QueryInterface` auf "ICorDebugValue" mit `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="229f2-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="229f2-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="229f2-113">Requirements</span></span>  
 <span data-ttu-id="229f2-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="229f2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="229f2-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="229f2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="229f2-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="229f2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="229f2-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="229f2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="229f2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="229f2-118">See also</span></span>
- [<span data-ttu-id="229f2-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="229f2-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="229f2-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="229f2-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
