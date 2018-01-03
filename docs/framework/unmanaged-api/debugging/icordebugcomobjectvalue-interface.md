---
title: ICorDebugComObjectValue-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugComObjectValue
helpviewer_keywords: ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9adeec14e102ef575f24566980477a285f87ba40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="ce43d-102">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce43d-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="ce43d-103">Stellt Methoden zum Abrufen von Informationen, die einen Runtime callable Wrapper (RCW) zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ce43d-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce43d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ce43d-104">Methods</span></span>  
  
|<span data-ttu-id="ce43d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ce43d-105">Method</span></span>|<span data-ttu-id="ce43d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce43d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce43d-107">GetCachedInterfacePointers-Methode</span><span class="sxs-lookup"><span data-stu-id="ce43d-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="ce43d-108">Ruft die unformatierten Schnittstellenzeiger, der für den aktuellen RCW zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="ce43d-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="ce43d-109">GetCachedInterfaceTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="ce43d-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="ce43d-110">Stellt einen Enumerator für die Schnittstellentypen bereit, dass das aktuelle Objekt Groß-/Kleinschreibung beachtet oder als verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ce43d-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce43d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce43d-111">Remarks</span></span>  
 <span data-ttu-id="ce43d-112">Um zu überprüfen, ob eine Instanz einer "ICorDebugValue"-Schnittstelle einen RCW darstellt, ein Debugger ruft `QueryInterface` auf "ICorDebugValue" mit `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="ce43d-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce43d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce43d-113">Requirements</span></span>  
 <span data-ttu-id="ce43d-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce43d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce43d-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce43d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce43d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce43d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce43d-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce43d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce43d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce43d-118">See Also</span></span>  
 [<span data-ttu-id="ce43d-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ce43d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ce43d-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ce43d-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
