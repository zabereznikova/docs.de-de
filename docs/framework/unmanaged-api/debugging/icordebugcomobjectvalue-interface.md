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
ms.openlocfilehash: 528db447df4d71d67441b05ad29e6a900c59afbb
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892819"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="3a799-102">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a799-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="3a799-103">Stellt Methoden bereit, um Informationen abzurufen, die einem Runtime Callable Wrapper (RCW) zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3a799-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a799-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3a799-104">Methods</span></span>  
  
|<span data-ttu-id="3a799-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3a799-105">Method</span></span>|<span data-ttu-id="3a799-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a799-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a799-107">GetCachedInterfacePointers-Methode</span><span class="sxs-lookup"><span data-stu-id="3a799-107">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="3a799-108">Ruft die unformatierten Schnittstellen Zeiger ab, die im aktuellen RCW zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="3a799-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="3a799-109">GetCachedInterfaceTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="3a799-109">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="3a799-110">Stellt einen Enumerator für die Schnittstellentypen bereit, in die das aktuelle-Objekt geschrieben oder verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="3a799-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a799-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3a799-111">Remarks</span></span>  
 <span data-ttu-id="3a799-112">Um zu überprüfen, ob eine Instanz der Schnittstelle "ICorDebugValue" einen RCW darstellt, ruft `QueryInterface` ein Debugger mit `IID_ICorDebugComObjectValue`"ICorDebugValue" auf.</span><span class="sxs-lookup"><span data-stu-id="3a799-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a799-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a799-113">Requirements</span></span>  
 <span data-ttu-id="3a799-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a799-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a799-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a799-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a799-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a799-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a799-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a799-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a799-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a799-118">See also</span></span>

- [<span data-ttu-id="3a799-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3a799-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3a799-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="3a799-120">Debugging</span></span>](index.md)
