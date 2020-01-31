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
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790429"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="bdeab-102">IXCLRDataMethodDefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdeab-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="bdeab-103">Stellt Methoden zum Abfragen von Informationen über eine Methoden Definition bereit.</span><span class="sxs-lookup"><span data-stu-id="bdeab-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="bdeab-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bdeab-104">Methods</span></span>

<span data-ttu-id="bdeab-105">Die folgenden Methoden sind einige der Methoden, die in der-Schnittstelle verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="bdeab-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="bdeab-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="bdeab-106">Method</span></span>                                                                                                                          | <span data-ttu-id="bdeab-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bdeab-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="bdeab-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="bdeab-108">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="bdeab-109">Stellt ein Handle für die Enumeration von Methoden Instanzen für eine angegebene `IXCLRDataAppDomain`bereit.</span><span class="sxs-lookup"><span data-stu-id="bdeab-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="bdeab-110">Enuminstance</span><span class="sxs-lookup"><span data-stu-id="bdeab-110">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="bdeab-111">Listet die Instanzen dieser Methoden Definition auf.</span><span class="sxs-lookup"><span data-stu-id="bdeab-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="bdeab-112">Enumuminstance</span><span class="sxs-lookup"><span data-stu-id="bdeab-112">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="bdeab-113">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der instanzenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bdeab-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="bdeab-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bdeab-114">Remarks</span></span>

<span data-ttu-id="bdeab-115">Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt.</span><span class="sxs-lookup"><span data-stu-id="bdeab-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="bdeab-116">Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit GUID-`AAF60008-FB2C-420b-8FB1-42D244A54A97` abgeleitet ist, die über die üblichen com-Mechanismen abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="bdeab-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="bdeab-117">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bdeab-117">Requirements</span></span>

<span data-ttu-id="bdeab-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdeab-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bdeab-119">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="bdeab-119">**Header:** None</span></span>  
<span data-ttu-id="bdeab-120">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="bdeab-120">**Library:** None</span></span>  
<span data-ttu-id="bdeab-121">**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bdeab-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="bdeab-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdeab-122">See also</span></span>

- [<span data-ttu-id="bdeab-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bdeab-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="bdeab-124">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bdeab-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
