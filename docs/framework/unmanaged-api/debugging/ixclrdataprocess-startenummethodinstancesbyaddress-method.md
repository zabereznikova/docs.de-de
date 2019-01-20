---
title: IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
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
ms.openlocfilehash: 88ce9dd928871d71058fe28c243a9fb51b729778
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416465"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="6182e-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span><span class="sxs-lookup"><span data-stu-id="6182e-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="6182e-103">Stellt ein Handle zum Auflisten von der Methodeninstanzen von `AppDomain` ab einer angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="6182e-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6182e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6182e-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

### <a name="parameters"></a><span data-ttu-id="6182e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6182e-105">Parameters</span></span>

<span data-ttu-id="6182e-106">`address` [in] Die Adresse der ersten Methodeninstanz.</span><span class="sxs-lookup"><span data-stu-id="6182e-106">`address` [in] The address of the first method instance.</span></span>

<span data-ttu-id="6182e-107">`appDomain` [in] Die AppDomain der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="6182e-107">`appDomain` [in] The AppDomain of the method instances.</span></span>

<span data-ttu-id="6182e-108">`handle` [out] Ein Handle für das Auflisten der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="6182e-108">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="6182e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6182e-109">Remarks</span></span>

<span data-ttu-id="6182e-110">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 27. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="6182e-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6182e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6182e-111">Requirements</span></span>

<span data-ttu-id="6182e-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6182e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6182e-113">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="6182e-113">**Header:** None</span></span>  
<span data-ttu-id="6182e-114">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="6182e-114">**Library:** None</span></span>  
<span data-ttu-id="6182e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6182e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6182e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6182e-116">See Also</span></span>

- [<span data-ttu-id="6182e-117">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6182e-117">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6182e-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6182e-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6182e-119">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6182e-119">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
