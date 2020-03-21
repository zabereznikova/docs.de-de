---
title: IXCLRDataProcess::EnumMethodInstanceByAddress-Methode
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
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176655"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="87866-102">IXCLRDataProcess::EnumMethodInstanceByAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="87866-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="87866-103">Zählt die Methodeninstanzen dieses Prozesses auf, beginnend mit einem Adressoffset.</span><span class="sxs-lookup"><span data-stu-id="87866-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="87866-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87866-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="87866-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="87866-105">Parameters</span></span>

`handle`\
<span data-ttu-id="87866-106">[in] Ein Handle zum Aufzählen der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="87866-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="87866-107">[out] Die aufgezählte Methodeninstanz.</span><span class="sxs-lookup"><span data-stu-id="87866-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="87866-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="87866-108">Remarks</span></span>

<span data-ttu-id="87866-109">Die bereitgestellte Methode `IXCLRDataProcess` ist Teil der Schnittstelle und entspricht dem 28. Slot der virtuellen Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="87866-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="87866-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="87866-110">Requirements</span></span>

<span data-ttu-id="87866-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87866-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="87866-112">**Kopfzeile:** Keine **Bibliothek:** Keine **.NET Framework-Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="87866-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="87866-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87866-113">See also</span></span>

- [<span data-ttu-id="87866-114">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="87866-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="87866-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="87866-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="87866-116">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87866-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
