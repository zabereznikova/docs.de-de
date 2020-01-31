---
title: ICorDebugAppDomainEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: 9fb849c78636d5e29f58a70f59aa4cb3cd22df40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784736"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="49f2b-102">ICorDebugAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49f2b-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="49f2b-103">Stellt die `Next`-Methode bereit, die eine angegebene Anzahl von `ICorDebugAppDomainEnum` Werten zurückgibt, beginnend an der nächsten Position in der-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="49f2b-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="49f2b-104">Bei dieser Schnittstelle handelt es sich um eine Unterklasse von "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="49f2b-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49f2b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="49f2b-105">Methods</span></span>  
  
|<span data-ttu-id="49f2b-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="49f2b-106">Method</span></span>|<span data-ttu-id="49f2b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49f2b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49f2b-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="49f2b-108">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="49f2b-109">Ruft die angegebene Anzahl von Anwendungs Domänen ab der aktuellen Cursorposition aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="49f2b-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49f2b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49f2b-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49f2b-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="49f2b-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49f2b-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49f2b-112">Requirements</span></span>  
 <span data-ttu-id="49f2b-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49f2b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49f2b-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49f2b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49f2b-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49f2b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49f2b-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49f2b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f2b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49f2b-117">See also</span></span>

- [<span data-ttu-id="49f2b-118">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49f2b-118">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="49f2b-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="49f2b-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
