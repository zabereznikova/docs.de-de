---
title: 'Ixclrdatamethoddefinition:: enuminstance-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ae1ef2a3c8cf9e042ab9ab233ed993f8e36b2fce
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420941"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="6963c-102">Ixclrdatamethoddefinition:: enuminstance-Methode</span><span class="sxs-lookup"><span data-stu-id="6963c-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="6963c-103">Listet die Instanzen dieser Methoden Definition auf.</span><span class="sxs-lookup"><span data-stu-id="6963c-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6963c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6963c-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="6963c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6963c-105">Parameters</span></span>

`handle`\
<span data-ttu-id="6963c-106">[in, out] Ein Handle zum Auflisten der-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="6963c-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="6963c-107">vorgenommen Die Enumerationsinstanz.</span><span class="sxs-lookup"><span data-stu-id="6963c-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="6963c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6963c-108">Remarks</span></span>

<span data-ttu-id="6963c-109">Die bereitgestellte Methode ist Teil der `IXCLRDataMethodDefinition` -Schnittstelle und entspricht dem sechsten Slot der virtuellen Methoden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6963c-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6963c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6963c-110">Requirements</span></span>

<span data-ttu-id="6963c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6963c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6963c-112">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="6963c-112">**Header:** None</span></span>  
<span data-ttu-id="6963c-113">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="6963c-113">**Library:** None</span></span>  
<span data-ttu-id="6963c-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6963c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6963c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6963c-115">See also</span></span>

- [<span data-ttu-id="6963c-116">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6963c-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6963c-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6963c-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="6963c-118">IXCLRDataMethodDefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6963c-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="6963c-119">IXCLRDataMethodInstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6963c-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
