---
title: IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a48a7fc9a141354666c50b1f6da8f1aaa180ff6c
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416428"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="bcad2-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span><span class="sxs-lookup"><span data-stu-id="bcad2-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="bcad2-103">Gibt die vom internen Iteratoren, die verwendet werden, während der Instanzenumeration verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="bcad2-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="bcad2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bcad2-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="bcad2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bcad2-105">Parameters</span></span>

<span data-ttu-id="bcad2-106">`handle` [out] Ein Handle für das Auflisten der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="bcad2-106">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="bcad2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bcad2-107">Remarks</span></span>

<span data-ttu-id="bcad2-108">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 29. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="bcad2-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bcad2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bcad2-109">Requirements</span></span>

<span data-ttu-id="bcad2-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcad2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bcad2-111">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="bcad2-111">**Header:** None</span></span>  
<span data-ttu-id="bcad2-112">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="bcad2-112">**Library:** None</span></span>  
<span data-ttu-id="bcad2-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bcad2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="bcad2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcad2-114">See Also</span></span>

- [<span data-ttu-id="bcad2-115">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="bcad2-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="bcad2-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="bcad2-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="bcad2-117">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bcad2-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
