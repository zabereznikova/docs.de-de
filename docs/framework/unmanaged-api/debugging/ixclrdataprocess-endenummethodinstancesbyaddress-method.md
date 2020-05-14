---
title: 'Ixclrdataprocess:: dendenummethodinstancesbyaddress-Methode'
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
ms.openlocfilehash: 04ce8f44b0c9f532951666de7bfb9de475c14746
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395261"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="438d1-102">Ixclrdataprocess:: dendenummethodinstancesbyaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="438d1-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="438d1-103">Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der instanzenumeration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="438d1-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="438d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="438d1-104">Syntax</span></span>

```cpp
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="438d1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="438d1-105">Parameters</span></span>

`handle`\
<span data-ttu-id="438d1-106">vorgenommen Ein Handle zum Auflisten der Methoden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="438d1-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="438d1-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="438d1-107">Remarks</span></span>

<span data-ttu-id="438d1-108">Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 30. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="438d1-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 30th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="438d1-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="438d1-109">Requirements</span></span>

<span data-ttu-id="438d1-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="438d1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="438d1-111">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="438d1-111">**Header:** None</span></span>  
<span data-ttu-id="438d1-112">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="438d1-112">**Library:** None</span></span>  
<span data-ttu-id="438d1-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="438d1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="438d1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="438d1-114">See also</span></span>

- [<span data-ttu-id="438d1-115">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="438d1-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="438d1-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="438d1-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="438d1-117">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="438d1-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
