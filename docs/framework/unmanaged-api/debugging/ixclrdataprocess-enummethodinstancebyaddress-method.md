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
ms.openlocfilehash: b42939e8e64e75337478ace67a9a91c6a03a94e3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416462"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="b7a65-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span><span class="sxs-lookup"><span data-stu-id="b7a65-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="b7a65-103">Listet die Methodeninstanzen dieses Prozesses, der einen Adressoffset ab.</span><span class="sxs-lookup"><span data-stu-id="b7a65-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b7a65-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7a65-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

### <a name="parameters"></a><span data-ttu-id="b7a65-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7a65-105">Parameters</span></span>

<span data-ttu-id="b7a65-106">`handle` [in] Ein Handle für das Auflisten der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="b7a65-106">`handle` [in] A handle for enumerating the method instances.</span></span>

<span data-ttu-id="b7a65-107">`mod` [out] Die aufgelisteten Methodeninstanz.</span><span class="sxs-lookup"><span data-stu-id="b7a65-107">`mod` [out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7a65-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7a65-108">Remarks</span></span>

<span data-ttu-id="b7a65-109">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 28. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="b7a65-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7a65-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7a65-110">Requirements</span></span>

<span data-ttu-id="b7a65-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7a65-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="b7a65-112">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="b7a65-112">**Header:** None</span></span>   
<span data-ttu-id="b7a65-113">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="b7a65-113">**Library:** None</span></span>   
<span data-ttu-id="b7a65-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b7a65-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="b7a65-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7a65-115">See Also</span></span>
- [<span data-ttu-id="b7a65-116">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b7a65-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b7a65-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b7a65-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b7a65-118">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b7a65-118">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
