---
title: 'Ixclrdataprocess:: enummodule-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5caadcfe091393a8ff79106d57a50a532c349829
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420773"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="e94d6-102">Ixclrdataprocess:: enummodule-Methode</span><span class="sxs-lookup"><span data-stu-id="e94d6-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="e94d6-103">Listet die Module dieses Prozesses auf.</span><span class="sxs-lookup"><span data-stu-id="e94d6-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e94d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e94d6-104">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="e94d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e94d6-105">Parameters</span></span>

`handle`\
<span data-ttu-id="e94d6-106">[in, out] Ein Handle zum Auflisten der Module.</span><span class="sxs-lookup"><span data-stu-id="e94d6-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="e94d6-107">vorgenommen Das-enumerationsmodul.</span><span class="sxs-lookup"><span data-stu-id="e94d6-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="e94d6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e94d6-108">Remarks</span></span>

<span data-ttu-id="e94d6-109">Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 25. Slot der virtuellen Methoden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e94d6-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e94d6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e94d6-110">Requirements</span></span>

<span data-ttu-id="e94d6-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e94d6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e94d6-112">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="e94d6-112">**Header:** None</span></span>  
<span data-ttu-id="e94d6-113">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="e94d6-113">**Library:** None</span></span>  
<span data-ttu-id="e94d6-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e94d6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e94d6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e94d6-115">See also</span></span>

- [<span data-ttu-id="e94d6-116">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e94d6-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="e94d6-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e94d6-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="e94d6-118">IXCLRDataModule Interface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e94d6-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="e94d6-119">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e94d6-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
