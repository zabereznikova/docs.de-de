---
title: 'Ixclrdatamethodinstance:: getrepresentativeentryaddress-Methode'
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: d9f9e16d243c0f3b45ac24776caea5bb9c32dcc1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395750"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="e9e05-102">Ixclrdatamethodinstance:: getrepresentativeentryaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="e9e05-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="e9e05-103">Ruft die für die systeminterne Kompilierung aller möglichen Einstiegspunkte einer Methode die am meisten repräsentative Einstiegspunkt Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="e9e05-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e9e05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9e05-104">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="e9e05-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9e05-105">Parameters</span></span>

`addr`\
<span data-ttu-id="e9e05-106">vorgenommen Die Adresse des repräsentativsten systemeigenen Einstiegs Punkts für die Methode.</span><span class="sxs-lookup"><span data-stu-id="e9e05-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9e05-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e9e05-107">Remarks</span></span>

<span data-ttu-id="e9e05-108">Die bereitgestellte Methode ist Teil der- [ `IXCLRDataMethodInstance` Schnittstelle](ixclrdatamethodinstance-interface.md) und entspricht dem 20. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="e9e05-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e9e05-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9e05-109">Requirements</span></span>

<span data-ttu-id="e9e05-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9e05-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e9e05-111">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="e9e05-111">**Header:** None</span></span>  
<span data-ttu-id="e9e05-112">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="e9e05-112">**Library:** None</span></span>  
<span data-ttu-id="e9e05-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e9e05-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e9e05-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9e05-114">See also</span></span>

- [<span data-ttu-id="e9e05-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e9e05-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="e9e05-116">IXCLRDataMethodInstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9e05-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
