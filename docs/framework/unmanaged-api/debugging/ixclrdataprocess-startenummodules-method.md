---
title: IXCLRDataProcess::StartEnumModules-Methode
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
ms.openlocfilehash: a81da147c1483e7649612050f4aba29a2cc63b49
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416480"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="6510c-102">IXCLRDataProcess::StartEnumModules-Methode</span><span class="sxs-lookup"><span data-stu-id="6510c-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="6510c-103">Stellt ein Handle zum Auflisten von der Modules eines Prozesses.</span><span class="sxs-lookup"><span data-stu-id="6510c-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6510c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6510c-104">Syntax</span></span>

```
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

### <a name="parameters"></a><span data-ttu-id="6510c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6510c-105">Parameters</span></span>

<span data-ttu-id="6510c-106">`handle` [out] Ein Handle für das Auflisten der Module.</span><span class="sxs-lookup"><span data-stu-id="6510c-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="6510c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6510c-107">Remarks</span></span>

<span data-ttu-id="6510c-108">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 24. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="6510c-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6510c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6510c-109">Requirements</span></span>

<span data-ttu-id="6510c-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6510c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6510c-111">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="6510c-111">**Header:** None</span></span>  
<span data-ttu-id="6510c-112">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="6510c-112">**Library:** None</span></span>  
<span data-ttu-id="6510c-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6510c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6510c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6510c-114">See Also</span></span>

- [<span data-ttu-id="6510c-115">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6510c-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6510c-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6510c-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6510c-117">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6510c-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
