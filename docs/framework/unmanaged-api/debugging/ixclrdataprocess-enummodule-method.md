---
title: IXCLRDataProcess::EnumModule-Methode
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
ms.openlocfilehash: a0398d18f9568754231082d63b4c6a2c865d8c6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775264"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="05903-102">IXCLRDataProcess::EnumModule-Methode</span><span class="sxs-lookup"><span data-stu-id="05903-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="05903-103">Listet die Module dieses Prozesses auf.</span><span class="sxs-lookup"><span data-stu-id="05903-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="05903-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05903-104">Syntax</span></span>

```
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="05903-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05903-105">Parameters</span></span>

`handle`\
<span data-ttu-id="05903-106">[in, out] Ein Handle für das Auflisten der Module.</span><span class="sxs-lookup"><span data-stu-id="05903-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="05903-107">[out] Die aufgelisteten-Modul.</span><span class="sxs-lookup"><span data-stu-id="05903-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="05903-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05903-108">Remarks</span></span>

<span data-ttu-id="05903-109">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 25. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="05903-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="05903-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="05903-110">Requirements</span></span>

<span data-ttu-id="05903-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05903-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="05903-112">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="05903-112">**Header:** None</span></span>  
<span data-ttu-id="05903-113">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="05903-113">**Library:** None</span></span>  
<span data-ttu-id="05903-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="05903-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="05903-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05903-115">See also</span></span>

- [<span data-ttu-id="05903-116">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="05903-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="05903-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="05903-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="05903-118">IXCLRDataModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05903-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="05903-119">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05903-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
