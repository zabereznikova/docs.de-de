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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da1fc949109455cf50767191a99a8a727116f77c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155193"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="7f373-102">ICorDebugAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f373-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="7f373-103">Stellt die `Next` Methode, die eine angegebene Anzahl von zurückgibt `ICorDebugAppDomainEnum` Werte, die mit der nächsten Position in der Enumeration beginnen.</span><span class="sxs-lookup"><span data-stu-id="7f373-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="7f373-104">Diese Schnittstelle ist eine Unterklasse von "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="7f373-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f373-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7f373-105">Methods</span></span>  
  
|<span data-ttu-id="7f373-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7f373-106">Method</span></span>|<span data-ttu-id="7f373-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f373-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f373-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="7f373-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="7f373-109">Ruft die angegebene Anzahl von Anwendungsdomänen aus der Auflistung, beginnend ab der aktuellen Cursorposition ab.</span><span class="sxs-lookup"><span data-stu-id="7f373-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f373-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7f373-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f373-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7f373-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f373-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7f373-112">Requirements</span></span>  
 <span data-ttu-id="7f373-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f373-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f373-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f373-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f373-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f373-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f373-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f373-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f373-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f373-117">See also</span></span>

- [<span data-ttu-id="7f373-118">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f373-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="7f373-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7f373-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
