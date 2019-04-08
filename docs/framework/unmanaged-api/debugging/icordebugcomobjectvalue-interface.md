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
ms.openlocfilehash: 3387985ebf6027b9cd9dee372190da65939dbae3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098623"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="5f127-102">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f127-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="5f127-103">Stellt Methoden zum Abrufen von Informationen, die einen Runtime callable Wrapper (RCW) zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5f127-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f127-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5f127-104">Methods</span></span>  
  
|<span data-ttu-id="5f127-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5f127-105">Method</span></span>|<span data-ttu-id="5f127-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f127-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f127-107">GetCachedInterfacePointers-Methode</span><span class="sxs-lookup"><span data-stu-id="5f127-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="5f127-108">Ruft den unformatierten Schnittstellenzeiger, der für den aktuellen RCW zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="5f127-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="5f127-109">GetCachedInterfaceTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="5f127-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="5f127-110">Stellt einen Enumerator für die Schnittstellentypen bereit, dass das aktuelle Objekt Groß-/Kleinschreibung beachtet oder als verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5f127-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f127-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f127-111">Remarks</span></span>  
 <span data-ttu-id="5f127-112">Um zu überprüfen, ob eine Instanz einer Schnittstelle "ICorDebugValue" einen RCW darstellt, ein Debugger ruft `QueryInterface` auf "ICorDebugValue" mit `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="5f127-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f127-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f127-113">Requirements</span></span>  
 <span data-ttu-id="5f127-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f127-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f127-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f127-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f127-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f127-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5f127-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5f127-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5f127-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f127-118">See also</span></span>

- [<span data-ttu-id="5f127-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5f127-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5f127-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5f127-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
