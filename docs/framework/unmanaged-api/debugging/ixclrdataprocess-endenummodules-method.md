---
title: IXCLRDataProcess::EndEnumModules-Methode
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
ms.openlocfilehash: de30384b4c12c4fcac3eafe580484685f8a43fa4
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611431"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="a1ed1-102">IXCLRDataProcess::EndEnumModules-Methode</span><span class="sxs-lookup"><span data-stu-id="a1ed1-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="a1ed1-103">Gibt die Ressourcen, die von internen Iteratoren, die verwendet werden, während der Modul-Enumeration verwendet.</span><span class="sxs-lookup"><span data-stu-id="a1ed1-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a1ed1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1ed1-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="a1ed1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1ed1-105">Parameters</span></span>

`handle`\
<span data-ttu-id="a1ed1-106">[out] Ein Handle für das Auflisten der Module.</span><span class="sxs-lookup"><span data-stu-id="a1ed1-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1ed1-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1ed1-107">Remarks</span></span>

<span data-ttu-id="a1ed1-108">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 26. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="a1ed1-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1ed1-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1ed1-109">Requirements</span></span>

<span data-ttu-id="a1ed1-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1ed1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="a1ed1-111">**Header:** Keine **Bibliothek:** Keine **.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a1ed1-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a1ed1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1ed1-112">See also</span></span>

- [<span data-ttu-id="a1ed1-113">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a1ed1-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="a1ed1-114">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1ed1-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
