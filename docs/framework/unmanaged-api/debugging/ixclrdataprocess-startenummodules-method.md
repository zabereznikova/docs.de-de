---
title: 'Ixclrdataprocess:: startenummodules-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d55b07ea3fada73237919bf677163a9096d5ad04
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420720"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="aa183-102">Ixclrdataprocess:: startenummodules-Methode</span><span class="sxs-lookup"><span data-stu-id="aa183-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="aa183-103">Stellt ein Handle zum Auflisten der Module eines Prozesses bereit.</span><span class="sxs-lookup"><span data-stu-id="aa183-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="aa183-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa183-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="aa183-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa183-105">Parameters</span></span>

`handle`\
<span data-ttu-id="aa183-106">vorgenommen Ein Handle zum Auflisten der Module.</span><span class="sxs-lookup"><span data-stu-id="aa183-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa183-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa183-107">Remarks</span></span>

<span data-ttu-id="aa183-108">Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 24. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="aa183-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="aa183-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa183-109">Requirements</span></span>

<span data-ttu-id="aa183-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa183-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="aa183-111">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="aa183-111">**Header:** None</span></span>  
<span data-ttu-id="aa183-112">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="aa183-112">**Library:** None</span></span>  
<span data-ttu-id="aa183-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="aa183-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="aa183-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa183-114">See also</span></span>

- [<span data-ttu-id="aa183-115">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="aa183-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="aa183-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="aa183-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="aa183-117">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa183-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
