---
title: 'Ixclrdataprocess:: startenummethodinstancesbyaddress-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 52d533f1c86b34b7b9febade8590e7ab58d8221e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420733"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="bf942-102">Ixclrdataprocess:: startenummethodinstancesbyaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="bf942-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="bf942-103">Stellt ein Handle zum Auflisten der Methoden Instanzen von bereit, `AppDomain` beginnend bei einer angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="bf942-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="bf942-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf942-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="bf942-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bf942-105">Parameters</span></span>

`address`\
<span data-ttu-id="bf942-106">in Die Adresse der ersten Methoden Instanz.</span><span class="sxs-lookup"><span data-stu-id="bf942-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="bf942-107">in Die AppDomain der Methoden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="bf942-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="bf942-108">vorgenommen Ein Handle zum Auflisten der Methoden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="bf942-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf942-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf942-109">Remarks</span></span>

<span data-ttu-id="bf942-110">Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 28. Slot der virtuellen Methoden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bf942-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf942-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf942-111">Requirements</span></span>

<span data-ttu-id="bf942-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf942-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bf942-113">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="bf942-113">**Header:** None</span></span>  
<span data-ttu-id="bf942-114">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="bf942-114">**Library:** None</span></span>  
<span data-ttu-id="bf942-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bf942-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="bf942-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf942-116">See also</span></span>

- [<span data-ttu-id="bf942-117">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="bf942-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="bf942-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bf942-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="bf942-119">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf942-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
