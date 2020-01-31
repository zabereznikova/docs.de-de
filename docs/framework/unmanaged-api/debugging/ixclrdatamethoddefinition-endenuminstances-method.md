---
title: 'Ixclrdatamethoddefinition:: endenuminstance-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 605a4244d20ef6c0b7af3c2b26b65ff2a63fa9dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790449"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="31af2-102">Ixclrdatamethoddefinition:: endenuminstance-Methode</span><span class="sxs-lookup"><span data-stu-id="31af2-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="31af2-103">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der instanzenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31af2-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="31af2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31af2-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="31af2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="31af2-105">Parameters</span></span>

`handle`\
<span data-ttu-id="31af2-106">vorgenommen Ein Handle zum Auflisten der-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="31af2-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="31af2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31af2-107">Remarks</span></span>

<span data-ttu-id="31af2-108">Die bereitgestellte Methode ist Teil der `IXCLRDataMethodDefinition`-Schnittstelle und entspricht dem fünften Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="31af2-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="31af2-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31af2-109">Requirements</span></span>

<span data-ttu-id="31af2-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31af2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="31af2-111">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="31af2-111">**Header:** None</span></span>  
<span data-ttu-id="31af2-112">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="31af2-112">**Library:** None</span></span>  
<span data-ttu-id="31af2-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="31af2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="31af2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31af2-114">See also</span></span>

- [<span data-ttu-id="31af2-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="31af2-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="31af2-116">Ixclrdatamethoddefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31af2-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
