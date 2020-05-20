---
title: IXCLRDataProcess-Schnittstelle
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 6a6def8fc10f04b89aa8d8c735025b01f9b6ddfb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420759"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="33f65-102">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33f65-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="33f65-103">Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="33f65-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="33f65-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="33f65-104">Methods</span></span>

| <span data-ttu-id="33f65-105">Methode</span><span class="sxs-lookup"><span data-stu-id="33f65-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="33f65-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="33f65-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="33f65-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="33f65-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="33f65-108">Ruft ein `AppDomain` in einem Prozess anhand seiner eindeutigen ID ab.</span><span class="sxs-lookup"><span data-stu-id="33f65-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="33f65-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="33f65-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="33f65-110">Stellt ein Handle zum Auflisten der Module eines Prozesses bereit.</span><span class="sxs-lookup"><span data-stu-id="33f65-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="33f65-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="33f65-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="33f65-112">Listet die Module dieses Prozesses auf.</span><span class="sxs-lookup"><span data-stu-id="33f65-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="33f65-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="33f65-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="33f65-114">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der modulenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33f65-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="33f65-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="33f65-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="33f65-116">Stellt ein Handle zum Auflisten der Methoden Instanzen von bereit, `AppDomain` beginnend bei einer angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="33f65-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="33f65-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="33f65-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="33f65-118">Listet die Methoden Instanzen dieses Prozesses auf, beginnend bei einem Adress Offset.</span><span class="sxs-lookup"><span data-stu-id="33f65-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="33f65-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="33f65-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="33f65-120">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der instanzenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33f65-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="33f65-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33f65-121">Remarks</span></span>

<span data-ttu-id="33f65-122">Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt.</span><span class="sxs-lookup"><span data-stu-id="33f65-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="33f65-123">Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit der GUID abgeleitet ist `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` , die über die üblichen com-Mechanismen abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="33f65-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="33f65-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33f65-124">Requirements</span></span>

<span data-ttu-id="33f65-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33f65-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="33f65-126">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="33f65-126">**Header:** None</span></span>  
<span data-ttu-id="33f65-127">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="33f65-127">**Library:** None</span></span>  
<span data-ttu-id="33f65-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="33f65-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="33f65-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33f65-129">See also</span></span>

- [<span data-ttu-id="33f65-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="33f65-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="33f65-131">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="33f65-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
