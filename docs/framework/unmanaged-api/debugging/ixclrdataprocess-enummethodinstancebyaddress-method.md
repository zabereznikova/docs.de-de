---
title: IXCLRDataProcess::EnumMethodInstanceByAddress Method
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
ms.openlocfilehash: 825cb8ea94bee980f9e10b90cddf04db32c1a33f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491908"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="a7248-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span><span class="sxs-lookup"><span data-stu-id="a7248-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="a7248-103">Listet die Methodeninstanzen dieses Prozesses, der einen Adressoffset ab.</span><span class="sxs-lookup"><span data-stu-id="a7248-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a7248-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7248-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

### <a name="parameters"></a><span data-ttu-id="a7248-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7248-105">Parameters</span></span>

<span data-ttu-id="a7248-106">`handle` [in] Ein Handle für das Auflisten der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="a7248-106">`handle` [in] A handle for enumerating the method instances.</span></span>

<span data-ttu-id="a7248-107">`mod` [out] Die aufgelisteten Methodeninstanz.</span><span class="sxs-lookup"><span data-stu-id="a7248-107">`mod` [out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7248-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7248-108">Remarks</span></span>

<span data-ttu-id="a7248-109">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 28. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="a7248-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a7248-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7248-110">Requirements</span></span>

<span data-ttu-id="a7248-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7248-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="a7248-112">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="a7248-112">**Header:** None</span></span>   
<span data-ttu-id="a7248-113">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="a7248-113">**Library:** None</span></span>   
<span data-ttu-id="a7248-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a7248-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="a7248-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7248-115">See also</span></span>
- [<span data-ttu-id="a7248-116">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a7248-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a7248-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a7248-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="a7248-118">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7248-118">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
