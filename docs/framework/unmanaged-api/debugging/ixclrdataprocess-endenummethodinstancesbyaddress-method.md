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
ms.openlocfilehash: 072e775d11d44dfbca27f1616889e388ae61d467
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775478"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="87c12-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span><span class="sxs-lookup"><span data-stu-id="87c12-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="87c12-103">Gibt die vom internen Iteratoren, die verwendet werden, während der Instanzenumeration verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="87c12-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="87c12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87c12-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="87c12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="87c12-105">Parameters</span></span>

`handle`\
<span data-ttu-id="87c12-106">[out] Ein Handle für das Auflisten der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="87c12-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="87c12-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87c12-107">Remarks</span></span>

<span data-ttu-id="87c12-108">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 29. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="87c12-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="87c12-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="87c12-109">Requirements</span></span>

<span data-ttu-id="87c12-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87c12-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="87c12-111">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="87c12-111">**Header:** None</span></span>  
<span data-ttu-id="87c12-112">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="87c12-112">**Library:** None</span></span>  
<span data-ttu-id="87c12-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="87c12-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="87c12-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87c12-114">See also</span></span>

- [<span data-ttu-id="87c12-115">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="87c12-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="87c12-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="87c12-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="87c12-117">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87c12-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
