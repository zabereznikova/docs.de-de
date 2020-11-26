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
ms.openlocfilehash: 376ec2b840bc17c79ed1f27c17a8ddd22c37a0f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245353"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="82f61-102">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82f61-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="82f61-103">Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="82f61-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="82f61-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="82f61-104">Methods</span></span>

| <span data-ttu-id="82f61-105">Methode</span><span class="sxs-lookup"><span data-stu-id="82f61-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="82f61-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="82f61-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="82f61-107">Getruntimenamebyaddress</span><span class="sxs-lookup"><span data-stu-id="82f61-107">GetRuntimeNameByAddress</span></span>](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | <span data-ttu-id="82f61-108">Ruft einen Namen für die angegebene Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="82f61-108">Gets a name for the given address.</span></span>                                                               |
| [<span data-ttu-id="82f61-109">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="82f61-109">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="82f61-110">Ruft ein `AppDomain` in einem Prozess anhand seiner eindeutigen ID ab.</span><span class="sxs-lookup"><span data-stu-id="82f61-110">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="82f61-111">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="82f61-111">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="82f61-112">Stellt ein Handle zum Auflisten der Module eines Prozesses bereit.</span><span class="sxs-lookup"><span data-stu-id="82f61-112">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="82f61-113">EnumModule</span><span class="sxs-lookup"><span data-stu-id="82f61-113">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="82f61-114">Listet die Module dieses Prozesses auf.</span><span class="sxs-lookup"><span data-stu-id="82f61-114">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="82f61-115">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="82f61-115">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="82f61-116">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der modulenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82f61-116">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="82f61-117">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="82f61-117">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="82f61-118">Stellt ein Handle zum Auflisten der Methoden Instanzen von bereit, `AppDomain` beginnend bei einer angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="82f61-118">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="82f61-119">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="82f61-119">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="82f61-120">Listet die Methoden Instanzen dieses Prozesses auf, beginnend bei einem Adress Offset.</span><span class="sxs-lookup"><span data-stu-id="82f61-120">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="82f61-121">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="82f61-121">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="82f61-122">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der instanzenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82f61-122">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="82f61-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82f61-123">Remarks</span></span>

<span data-ttu-id="82f61-124">Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt.</span><span class="sxs-lookup"><span data-stu-id="82f61-124">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="82f61-125">Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit der GUID abgeleitet ist `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` , die über die üblichen com-Mechanismen abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="82f61-125">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="82f61-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82f61-126">Requirements</span></span>

<span data-ttu-id="82f61-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82f61-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="82f61-128">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="82f61-128">**Header:** None</span></span>  
<span data-ttu-id="82f61-129">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="82f61-129">**Library:** None</span></span>  
<span data-ttu-id="82f61-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="82f61-130">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="82f61-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82f61-131">See also</span></span>

- [<span data-ttu-id="82f61-132">Debuggen</span><span class="sxs-lookup"><span data-stu-id="82f61-132">Debugging</span></span>](index.md)
- [<span data-ttu-id="82f61-133">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="82f61-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
