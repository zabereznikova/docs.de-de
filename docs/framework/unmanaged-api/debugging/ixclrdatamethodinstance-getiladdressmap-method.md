---
title: 'Ixclrdatamethodinstance:: getiladdressmap-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 0acfa9ffd6f4bc3be567855008dccd08c9c74153
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420915"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="57e62-102">Ixclrdatamethodinstance:: getiladdressmap-Methode</span><span class="sxs-lookup"><span data-stu-id="57e62-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="57e62-103">Ruft die Il zum Adressieren von Zuordnungsinformationen ab</span><span class="sxs-lookup"><span data-stu-id="57e62-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="57e62-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="57e62-104">Syntax</span></span>

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="57e62-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="57e62-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="57e62-106">in Die Länge des bereitgestellten Maps-Arrays.</span><span class="sxs-lookup"><span data-stu-id="57e62-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="57e62-107">vorgenommen Die Anzahl der Karten Einträge, die von der Methode benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="57e62-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="57e62-108">[out, size_is (maplen)] Das Array zum Speichern der Karten Einträge.</span><span class="sxs-lookup"><span data-stu-id="57e62-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="57e62-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57e62-109">Remarks</span></span>

<span data-ttu-id="57e62-110">Die bereitgestellte Methode ist Teil der `IXCLRDataMethodInstance` -Schnittstelle und entspricht dem 15. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="57e62-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 15th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="57e62-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57e62-111">Requirements</span></span>

<span data-ttu-id="57e62-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57e62-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="57e62-113">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="57e62-113">**Header:** None</span></span>  
<span data-ttu-id="57e62-114">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="57e62-114">**Library:** None</span></span>  
<span data-ttu-id="57e62-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="57e62-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="57e62-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57e62-116">See also</span></span>

- [<span data-ttu-id="57e62-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="57e62-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="57e62-118">IXCLRDataMethodInstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57e62-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
