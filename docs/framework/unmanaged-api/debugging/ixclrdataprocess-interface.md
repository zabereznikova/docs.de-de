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
ms.openlocfilehash: ff74a7acb5cc84c177f083c19402cd78977aeab5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680373"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="94a3a-102">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94a3a-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="94a3a-103">Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="94a3a-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="94a3a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="94a3a-104">Methods</span></span>

| <span data-ttu-id="94a3a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="94a3a-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="94a3a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94a3a-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="94a3a-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="94a3a-107">GetAppDomainByUniqueId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="94a3a-108">Ruft eine `AppDomain` in einem Prozess über ihren eindeutigen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="94a3a-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="94a3a-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="94a3a-109">StartEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="94a3a-110">Stellt ein Handle zum Auflisten von der Modules eines Prozesses.</span><span class="sxs-lookup"><span data-stu-id="94a3a-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="94a3a-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="94a3a-111">EnumModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="94a3a-112">Listet die Module dieses Prozesses auf.</span><span class="sxs-lookup"><span data-stu-id="94a3a-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="94a3a-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="94a3a-113">EndEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="94a3a-114">Gibt die Ressourcen, die von internen Iteratoren, die verwendet werden, während der Modul-Enumeration verwendet.</span><span class="sxs-lookup"><span data-stu-id="94a3a-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="94a3a-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="94a3a-115">StartEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="94a3a-116">Stellt ein Handle zum Auflisten von der Methodeninstanzen von `AppDomain` ab einer angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="94a3a-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="94a3a-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="94a3a-117">EnumMethodInstanceByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="94a3a-118">Listet die Methodeninstanzen dieses Prozesses, der einen Adressoffset ab.</span><span class="sxs-lookup"><span data-stu-id="94a3a-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="94a3a-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="94a3a-119">EndEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="94a3a-120">Gibt die vom internen Iteratoren, die verwendet werden, während der Instanzenumeration verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="94a3a-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="94a3a-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94a3a-121">Remarks</span></span>

<span data-ttu-id="94a3a-122">Diese Schnittstelle befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="94a3a-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="94a3a-123">Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` , die über die üblichen Mechanismen der COM-abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="94a3a-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="94a3a-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94a3a-124">Requirements</span></span>

<span data-ttu-id="94a3a-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94a3a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="94a3a-126">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="94a3a-126">**Header:** None</span></span>  
<span data-ttu-id="94a3a-127">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="94a3a-127">**Library:** None</span></span>  
<span data-ttu-id="94a3a-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="94a3a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="94a3a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94a3a-129">See also</span></span>

- [<span data-ttu-id="94a3a-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="94a3a-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="94a3a-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="94a3a-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
