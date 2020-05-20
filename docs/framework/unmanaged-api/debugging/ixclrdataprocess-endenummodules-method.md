---
title: 'Ixclrdataprocess:: sdenummodules-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9a7a23e53f5c2bc7d643046830cf335fec780f11
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420837"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="67d65-102">Ixclrdataprocess:: sdenummodules-Methode</span><span class="sxs-lookup"><span data-stu-id="67d65-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="67d65-103">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der modulenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="67d65-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="67d65-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67d65-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="67d65-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67d65-105">Parameters</span></span>

`handle`\
<span data-ttu-id="67d65-106">vorgenommen Ein Handle zum Auflisten der Module.</span><span class="sxs-lookup"><span data-stu-id="67d65-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="67d65-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67d65-107">Remarks</span></span>

<span data-ttu-id="67d65-108">Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 26. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="67d65-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="67d65-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67d65-109">Requirements</span></span>

<span data-ttu-id="67d65-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67d65-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="67d65-111">**Header:** Keine **Bibliothek:** keine **.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="67d65-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="67d65-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67d65-112">See also</span></span>

- [<span data-ttu-id="67d65-113">Debuggen</span><span class="sxs-lookup"><span data-stu-id="67d65-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="67d65-114">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67d65-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
