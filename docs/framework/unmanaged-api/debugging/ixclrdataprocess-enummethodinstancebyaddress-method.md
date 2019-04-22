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
ms.openlocfilehash: a51c709b0b331127b74d98c4dc42e2772fd7f2db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166438"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="b745e-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span><span class="sxs-lookup"><span data-stu-id="b745e-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="b745e-103">Listet die Methodeninstanzen dieses Prozesses, der einen Adressoffset ab.</span><span class="sxs-lookup"><span data-stu-id="b745e-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b745e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b745e-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="b745e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b745e-105">Parameters</span></span>

`handle`\
<span data-ttu-id="b745e-106">[in] Ein Handle für das Auflisten der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="b745e-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="b745e-107">[out] Die aufgelisteten Methodeninstanz.</span><span class="sxs-lookup"><span data-stu-id="b745e-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="b745e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b745e-108">Remarks</span></span>

<span data-ttu-id="b745e-109">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 28. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="b745e-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b745e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b745e-110">Requirements</span></span>

<span data-ttu-id="b745e-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b745e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="b745e-112">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="b745e-112">**Header:** None</span></span>   
<span data-ttu-id="b745e-113">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="b745e-113">**Library:** None</span></span>   
<span data-ttu-id="b745e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b745e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="b745e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b745e-115">See also</span></span>

- [<span data-ttu-id="b745e-116">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b745e-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b745e-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b745e-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="b745e-118">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b745e-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
