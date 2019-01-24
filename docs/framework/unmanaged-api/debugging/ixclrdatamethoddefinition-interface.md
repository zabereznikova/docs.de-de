---
title: IXCLRDataMethodDefinition-Schnittstelle
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4b1e8cb1cf34bb1c5ade1353351aab953e2b734a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644246"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="9faef-102">IXCLRDataMethodDefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9faef-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="9faef-103">Stellt Methoden zum Abfragen von Informationen zu einer Methodendefinition.</span><span class="sxs-lookup"><span data-stu-id="9faef-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="9faef-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9faef-104">Methods</span></span>

<span data-ttu-id="9faef-105">Die folgenden Methoden sind einige der Methoden in der Benutzeroberfläche zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9faef-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="9faef-106">Methode</span><span class="sxs-lookup"><span data-stu-id="9faef-106">Method</span></span>                                                                                                                          | <span data-ttu-id="9faef-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9faef-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="9faef-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="9faef-108">StartEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="9faef-109">Stellt ein Handle für die Enumeration der Methodeninstanzen für einen bestimmten `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="9faef-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="9faef-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="9faef-110">EnumInstance</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="9faef-111">Listet die Instanzen dieser Definition der Methode.</span><span class="sxs-lookup"><span data-stu-id="9faef-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="9faef-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="9faef-112">EndEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="9faef-113">Gibt die vom internen Iteratoren, die verwendet werden, während der Instanzenumeration verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="9faef-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="9faef-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9faef-114">Remarks</span></span>

<span data-ttu-id="9faef-115">Diese Schnittstelle befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="9faef-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9faef-116">Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` , die über die üblichen Mechanismen der COM-abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9faef-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="9faef-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9faef-117">Requirements</span></span>

<span data-ttu-id="9faef-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9faef-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9faef-119">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="9faef-119">**Header:** None</span></span>  
<span data-ttu-id="9faef-120">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="9faef-120">**Library:** None</span></span>  
<span data-ttu-id="9faef-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9faef-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9faef-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9faef-122">See also</span></span>

- [<span data-ttu-id="9faef-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9faef-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9faef-124">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9faef-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
