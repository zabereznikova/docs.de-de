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
ms.openlocfilehash: a5d707d61513b030e5968af28db3c2a606e4419b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790372"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="a0603-102">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0603-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="a0603-103">Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="a0603-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="a0603-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a0603-104">Methods</span></span>

| <span data-ttu-id="a0603-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="a0603-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="a0603-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0603-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="a0603-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="a0603-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="a0603-108">Ruft eine `AppDomain` in einem Prozess anhand der eindeutigen ID ab.</span><span class="sxs-lookup"><span data-stu-id="a0603-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="a0603-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="a0603-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="a0603-110">Stellt ein Handle zum Auflisten der Module eines Prozesses bereit.</span><span class="sxs-lookup"><span data-stu-id="a0603-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="a0603-111">Enummodule</span><span class="sxs-lookup"><span data-stu-id="a0603-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="a0603-112">Listet die Module dieses Prozesses auf.</span><span class="sxs-lookup"><span data-stu-id="a0603-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="a0603-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="a0603-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="a0603-114">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der modulenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0603-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="a0603-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="a0603-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="a0603-116">Stellt ein Handle zum Auflisten der Methoden Instanzen von `AppDomain` beginnend bei einer angegebenen Adresse bereit.</span><span class="sxs-lookup"><span data-stu-id="a0603-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="a0603-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="a0603-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="a0603-118">Listet die Methoden Instanzen dieses Prozesses auf, beginnend bei einem Adress Offset.</span><span class="sxs-lookup"><span data-stu-id="a0603-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="a0603-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="a0603-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="a0603-120">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der instanzenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0603-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="a0603-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0603-121">Remarks</span></span>

<span data-ttu-id="a0603-122">Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt.</span><span class="sxs-lookup"><span data-stu-id="a0603-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a0603-123">Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit GUID-`5c552ab6-fc09-4cb3-8e36-22fa03c798b7` abgeleitet ist, die über die üblichen com-Mechanismen abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="a0603-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="a0603-124">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0603-124">Requirements</span></span>

<span data-ttu-id="a0603-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0603-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="a0603-126">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="a0603-126">**Header:** None</span></span>  
<span data-ttu-id="a0603-127">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="a0603-127">**Library:** None</span></span>  
<span data-ttu-id="a0603-128">**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a0603-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a0603-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0603-129">See also</span></span>

- [<span data-ttu-id="a0603-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a0603-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="a0603-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a0603-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
