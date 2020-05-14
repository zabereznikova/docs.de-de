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
ms.openlocfilehash: febe6766c7a35228820421eee975c777988efd1f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396492"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="dd5bf-102">Ixclrdatamethoddefinition:: endenuminstance-Methode</span><span class="sxs-lookup"><span data-stu-id="dd5bf-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="dd5bf-103">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der instanzenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd5bf-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="dd5bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd5bf-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="dd5bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dd5bf-105">Parameters</span></span>

`handle`\
<span data-ttu-id="dd5bf-106">vorgenommen Ein Handle zum Auflisten der-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="dd5bf-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd5bf-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="dd5bf-107">Remarks</span></span>

<span data-ttu-id="dd5bf-108">Die bereitgestellte Methode ist Teil der `IXCLRDataMethodDefinition` -Schnittstelle und entspricht dem 7. Slot der virtuellen Methoden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="dd5bf-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="dd5bf-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd5bf-109">Requirements</span></span>

<span data-ttu-id="dd5bf-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd5bf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="dd5bf-111">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="dd5bf-111">**Header:** None</span></span>  
<span data-ttu-id="dd5bf-112">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="dd5bf-112">**Library:** None</span></span>  
<span data-ttu-id="dd5bf-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dd5bf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="dd5bf-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd5bf-114">See also</span></span>

- [<span data-ttu-id="dd5bf-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="dd5bf-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="dd5bf-116">IXCLRDataMethodDefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd5bf-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
