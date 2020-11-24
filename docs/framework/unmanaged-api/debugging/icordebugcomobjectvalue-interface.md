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
ms.openlocfilehash: 40df1416e68c86efe6d404119cb37277fe21ac56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677543"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="3fdca-102">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3fdca-102">ICorDebugComObjectValue Interface</span></span>

<span data-ttu-id="3fdca-103">Stellt Methoden bereit, um Informationen abzurufen, die einem Runtime Callable Wrapper (RCW) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3fdca-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3fdca-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3fdca-104">Methods</span></span>  
  
|<span data-ttu-id="3fdca-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3fdca-105">Method</span></span>|<span data-ttu-id="3fdca-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3fdca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3fdca-107">GetCachedInterfacePointers-Methode</span><span class="sxs-lookup"><span data-stu-id="3fdca-107">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="3fdca-108">Ruft die unformatierten Schnittstellen Zeiger ab, die im aktuellen RCW zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="3fdca-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="3fdca-109">GetCachedInterfaceTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="3fdca-109">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="3fdca-110">Stellt einen Enumerator für die Schnittstellentypen bereit, in die das aktuelle-Objekt geschrieben oder verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="3fdca-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fdca-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fdca-111">Remarks</span></span>  

 <span data-ttu-id="3fdca-112">Um zu überprüfen, ob eine Instanz der Schnittstelle "ICorDebugValue" einen RCW darstellt, Ruft ein Debugger `QueryInterface` mit "ICorDebugValue" auf `IID_ICorDebugComObjectValue` .</span><span class="sxs-lookup"><span data-stu-id="3fdca-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fdca-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3fdca-113">Requirements</span></span>  

 <span data-ttu-id="3fdca-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fdca-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fdca-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fdca-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fdca-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fdca-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fdca-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fdca-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fdca-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fdca-118">See also</span></span>

- [<span data-ttu-id="3fdca-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3fdca-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3fdca-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="3fdca-120">Debugging</span></span>](index.md)
