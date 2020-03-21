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
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178375"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="79791-102">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79791-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="79791-103">Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="79791-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="79791-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="79791-104">Methods</span></span>

| <span data-ttu-id="79791-105">Methode</span><span class="sxs-lookup"><span data-stu-id="79791-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="79791-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79791-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="79791-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="79791-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="79791-108">Ruft `AppDomain` einen in einem Prozess durch seine eindeutige ID ab.</span><span class="sxs-lookup"><span data-stu-id="79791-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="79791-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="79791-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="79791-110">Stellt ein Handle zum Aufzählen der Module eines Prozesses bereit.</span><span class="sxs-lookup"><span data-stu-id="79791-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="79791-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="79791-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="79791-112">Zählt die Module dieses Prozesses auf.</span><span class="sxs-lookup"><span data-stu-id="79791-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="79791-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="79791-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="79791-114">Gibt die Ressourcen frei, die von internen Iteratoren verwendet werden, die während der Modulenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79791-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="79791-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="79791-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="79791-116">Stellt ein Handle bereit, um die `AppDomain` Methodeninstanzen des Startens an einer bestimmten Adresse aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="79791-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="79791-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="79791-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="79791-118">Zählt die Methodeninstanzen dieses Prozesses auf, beginnend mit einem Adressoffset.</span><span class="sxs-lookup"><span data-stu-id="79791-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="79791-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="79791-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="79791-120">Gibt die Ressourcen frei, die von internen Iteratoren verwendet werden, die während der Instanzenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79791-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="79791-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="79791-121">Remarks</span></span>

<span data-ttu-id="79791-122">Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="79791-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="79791-123">Es handelt sich jedoch um eine COM-Schnittstelle, die `IUnknown` mit GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` abstammt und über die üblichen COM-Mechanismen abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="79791-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="79791-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="79791-124">Requirements</span></span>

<span data-ttu-id="79791-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79791-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="79791-126">**Kopfzeile:** nichts</span><span class="sxs-lookup"><span data-stu-id="79791-126">**Header:** None</span></span>  
<span data-ttu-id="79791-127">**Bibliothek:** nichts</span><span class="sxs-lookup"><span data-stu-id="79791-127">**Library:** None</span></span>  
<span data-ttu-id="79791-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="79791-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="79791-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79791-129">See also</span></span>

- [<span data-ttu-id="79791-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="79791-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="79791-131">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="79791-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
