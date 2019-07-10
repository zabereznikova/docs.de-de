---
title: IXCLRDataMethodInstance::GetILAddressMap-Methode
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
ms.openlocfilehash: 66e4768acff7ab735c6ac9e8f8f51a9511f7e371
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744684"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="5daf8-102">IXCLRDataMethodInstance::GetILAddressMap-Methode</span><span class="sxs-lookup"><span data-stu-id="5daf8-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="5daf8-103">Ruft den IL-Code mit Adressinformationen für die Zuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="5daf8-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5daf8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5daf8-104">Syntax</span></span>

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="5daf8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5daf8-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="5daf8-106">[in] Die Länge des Arrays bereitgestellten Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="5daf8-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="5daf8-107">[out] Die Anzahl der Map-Einträge, die die Methode muss.</span><span class="sxs-lookup"><span data-stu-id="5daf8-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="5daf8-108">[Out, size_is(mapLen)] Das Array zum Speichern der Map-Einträge.</span><span class="sxs-lookup"><span data-stu-id="5daf8-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="5daf8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5daf8-109">Remarks</span></span>

<span data-ttu-id="5daf8-110">Die angegebene Methode ist Teil der `IXCLRDataMethodInstance` Schnittstelle, und mit dem 14. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="5daf8-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5daf8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5daf8-111">Requirements</span></span>

<span data-ttu-id="5daf8-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5daf8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5daf8-113">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="5daf8-113">**Header:** None</span></span>  
<span data-ttu-id="5daf8-114">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="5daf8-114">**Library:** None</span></span>  
<span data-ttu-id="5daf8-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5daf8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5daf8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5daf8-116">See also</span></span>

- [<span data-ttu-id="5daf8-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5daf8-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="5daf8-118">IXCLRDataMethodInstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5daf8-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
