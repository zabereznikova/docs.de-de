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
ms.openlocfilehash: 37b6bcb48681704e3db47f81a51a9d21f00dfb37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723193"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="7cea4-102">ICorDebugAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cea4-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="7cea4-103">Stellt die- `Next` Methode bereit, die eine angegebene Anzahl von Werten zurückgibt, `ICorDebugAppDomainEnum` beginnend an der nächsten Position in der-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="7cea4-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="7cea4-104">Bei dieser Schnittstelle handelt es sich um eine Unterklasse von "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="7cea4-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7cea4-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7cea4-105">Methods</span></span>  
  
|<span data-ttu-id="7cea4-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7cea4-106">Method</span></span>|<span data-ttu-id="7cea4-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7cea4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7cea4-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="7cea4-108">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="7cea4-109">Ruft die angegebene Anzahl von Anwendungs Domänen ab der aktuellen Cursorposition aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="7cea4-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cea4-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cea4-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7cea4-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7cea4-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cea4-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7cea4-112">Requirements</span></span>  

 <span data-ttu-id="7cea4-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cea4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cea4-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cea4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cea4-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cea4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cea4-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cea4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cea4-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7cea4-117">See also</span></span>

- [<span data-ttu-id="7cea4-118">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cea4-118">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="7cea4-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7cea4-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
