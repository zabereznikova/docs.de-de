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
ms.openlocfilehash: 4ff5c0d470e6eb84eb8b526f5e8f74e5e1a8118a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125485"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="aec1d-102">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aec1d-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="aec1d-103">Stellt Methoden bereit, um Informationen abzurufen, die einem Runtime Callable Wrapper (RCW) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="aec1d-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aec1d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="aec1d-104">Methods</span></span>  
  
|<span data-ttu-id="aec1d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="aec1d-105">Method</span></span>|<span data-ttu-id="aec1d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aec1d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aec1d-107">GetCachedInterfacePointers-Methode</span><span class="sxs-lookup"><span data-stu-id="aec1d-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="aec1d-108">Ruft die unformatierten Schnittstellen Zeiger ab, die im aktuellen RCW zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="aec1d-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="aec1d-109">GetCachedInterfaceTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="aec1d-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="aec1d-110">Stellt einen Enumerator für die Schnittstellentypen bereit, in die das aktuelle-Objekt geschrieben oder verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="aec1d-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aec1d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aec1d-111">Remarks</span></span>  
 <span data-ttu-id="aec1d-112">Um zu überprüfen, ob eine Instanz einer ICorDebugValue-Schnittstelle einen RCW darstellt, Ruft ein Debugger `QueryInterface` für "ICorDebugValue" mit `IID_ICorDebugComObjectValue`auf.</span><span class="sxs-lookup"><span data-stu-id="aec1d-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aec1d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aec1d-113">Requirements</span></span>  
 <span data-ttu-id="aec1d-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aec1d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aec1d-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aec1d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aec1d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aec1d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aec1d-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aec1d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec1d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aec1d-118">See also</span></span>

- [<span data-ttu-id="aec1d-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="aec1d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="aec1d-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="aec1d-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
