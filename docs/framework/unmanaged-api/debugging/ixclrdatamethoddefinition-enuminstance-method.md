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
ms.openlocfilehash: b6393d7fa4853c230203521e665bbe89d7b228e2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790440"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="1d737-102">Ixclrdatamethoddefinition:: enuminstance-Methode</span><span class="sxs-lookup"><span data-stu-id="1d737-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="1d737-103">Listet die Instanzen dieser Methoden Definition auf.</span><span class="sxs-lookup"><span data-stu-id="1d737-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1d737-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d737-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="1d737-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1d737-105">Parameters</span></span>

`handle`\
<span data-ttu-id="1d737-106">[in, out] Ein Handle zum Auflisten der-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="1d737-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="1d737-107">vorgenommen Die Enumerationsinstanz.</span><span class="sxs-lookup"><span data-stu-id="1d737-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d737-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d737-108">Remarks</span></span>

<span data-ttu-id="1d737-109">Die bereitgestellte Methode ist Teil der `IXCLRDataMethodDefinition`-Schnittstelle und entspricht dem vierten Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="1d737-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1d737-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d737-110">Requirements</span></span>

<span data-ttu-id="1d737-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d737-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1d737-112">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="1d737-112">**Header:** None</span></span>  
<span data-ttu-id="1d737-113">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="1d737-113">**Library:** None</span></span>  
<span data-ttu-id="1d737-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1d737-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1d737-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d737-115">See also</span></span>

- [<span data-ttu-id="1d737-116">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1d737-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="1d737-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1d737-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="1d737-118">Ixclrdatamethoddefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d737-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="1d737-119">Ixclrdatamethodinstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d737-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
