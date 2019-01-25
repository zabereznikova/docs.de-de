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
ms.openlocfilehash: 50ad55674360d7b880af3ddf701cf17005f30ce7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722737"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="6c46e-102">IXCLRDataProcess::EndEnumModules-Methode</span><span class="sxs-lookup"><span data-stu-id="6c46e-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="6c46e-103">Gibt die Ressourcen, die von internen Iteratoren, die verwendet werden, während der Modul-Enumeration verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c46e-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6c46e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c46e-104">Syntax</span></span>
```
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="6c46e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c46e-105">Parameters</span></span>
<span data-ttu-id="6c46e-106">`handle` [out] Ein Handle für das Auflisten der Module.</span><span class="sxs-lookup"><span data-stu-id="6c46e-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c46e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c46e-107">Remarks</span></span>

<span data-ttu-id="6c46e-108">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 26. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="6c46e-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6c46e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c46e-109">Requirements</span></span>

<span data-ttu-id="6c46e-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c46e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="6c46e-111">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="6c46e-111">**Header:** None</span></span>   
<span data-ttu-id="6c46e-112">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="6c46e-112">**Library:** None</span></span>   
<span data-ttu-id="6c46e-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6c46e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   

## <a name="see-also"></a><span data-ttu-id="6c46e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c46e-114">See also</span></span>

- [<span data-ttu-id="6c46e-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6c46e-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6c46e-116">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c46e-116">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
