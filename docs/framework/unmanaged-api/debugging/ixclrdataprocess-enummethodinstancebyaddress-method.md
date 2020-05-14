---
title: 'Ixclrdataprocess:: enummethodinstancebyaddress-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: f3800a5980304394dd648111fe23a3bb0890c575
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395111"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="82b39-102">Ixclrdataprocess:: enummethodinstancebyaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="82b39-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="82b39-103">Listet die Methoden Instanzen dieses Prozesses auf, beginnend bei einem Adress Offset.</span><span class="sxs-lookup"><span data-stu-id="82b39-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="82b39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82b39-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="82b39-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82b39-105">Parameters</span></span>

`handle`\
<span data-ttu-id="82b39-106">in Ein Handle zum Auflisten der Methoden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="82b39-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="82b39-107">vorgenommen Die enumerationsmethodeninstanz.</span><span class="sxs-lookup"><span data-stu-id="82b39-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="82b39-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="82b39-108">Remarks</span></span>

<span data-ttu-id="82b39-109">Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 29. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="82b39-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="82b39-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82b39-110">Requirements</span></span>

<span data-ttu-id="82b39-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82b39-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="82b39-112">**Header:** Keine **Bibliothek:** keine **.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="82b39-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="82b39-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82b39-113">See also</span></span>

- [<span data-ttu-id="82b39-114">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="82b39-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="82b39-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="82b39-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="82b39-116">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82b39-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
