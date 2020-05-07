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
ms.openlocfilehash: 38603fb53b9cd6548595437b05c1e99ef208d940
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895096"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="e65e8-102">ICorDebugAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e65e8-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="e65e8-103">Stellt die `Next` -Methode bereit, die eine angegebene Anzahl `ICorDebugAppDomainEnum` von Werten zurückgibt, beginnend an der nächsten Position in der-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e65e8-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="e65e8-104">Bei dieser Schnittstelle handelt es sich um eine Unterklasse von "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="e65e8-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e65e8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e65e8-105">Methods</span></span>  
  
|<span data-ttu-id="e65e8-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e65e8-106">Method</span></span>|<span data-ttu-id="e65e8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e65e8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e65e8-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="e65e8-108">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="e65e8-109">Ruft die angegebene Anzahl von Anwendungs Domänen ab der aktuellen Cursorposition aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="e65e8-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e65e8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e65e8-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e65e8-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e65e8-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e65e8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e65e8-112">Requirements</span></span>  
 <span data-ttu-id="e65e8-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e65e8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e65e8-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e65e8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e65e8-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e65e8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e65e8-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e65e8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e65e8-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e65e8-117">See also</span></span>

- [<span data-ttu-id="e65e8-118">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e65e8-118">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="e65e8-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e65e8-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
