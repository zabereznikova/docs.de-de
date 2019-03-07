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
ms.openlocfilehash: 23b567e4119578fba2f8cd4ba47f66dcf56a3878
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496845"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="a123b-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span><span class="sxs-lookup"><span data-stu-id="a123b-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="a123b-103">Listet die Methodeninstanzen dieses Prozesses, der einen Adressoffset ab.</span><span class="sxs-lookup"><span data-stu-id="a123b-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a123b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a123b-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="a123b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a123b-105">Parameters</span></span>

`handle`\
<span data-ttu-id="a123b-106">[in] Ein Handle für das Auflisten der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="a123b-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="a123b-107">[out] Die aufgelisteten Methodeninstanz.</span><span class="sxs-lookup"><span data-stu-id="a123b-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="a123b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a123b-108">Remarks</span></span>

<span data-ttu-id="a123b-109">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 28. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="a123b-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a123b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a123b-110">Requirements</span></span>

<span data-ttu-id="a123b-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a123b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="a123b-112">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="a123b-112">**Header:** None</span></span>   
<span data-ttu-id="a123b-113">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="a123b-113">**Library:** None</span></span>   
<span data-ttu-id="a123b-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a123b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="a123b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a123b-115">See also</span></span>
- [<span data-ttu-id="a123b-116">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a123b-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a123b-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a123b-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="a123b-118">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a123b-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
