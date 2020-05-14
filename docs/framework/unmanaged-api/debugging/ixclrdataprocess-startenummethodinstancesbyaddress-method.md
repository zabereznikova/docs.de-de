---
title: 'Ixclrdataprocess:: startenummethodinstancesbyaddress-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e28fa73300e147ac07a2d325fbf517480bb73797
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394948"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="6805f-102">Ixclrdataprocess:: startenummethodinstancesbyaddress-Methode</span><span class="sxs-lookup"><span data-stu-id="6805f-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="6805f-103">Stellt ein Handle zum Auflisten der Methoden Instanzen von bereit, `AppDomain` beginnend bei einer angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="6805f-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6805f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6805f-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="6805f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6805f-105">Parameters</span></span>

`address`\
<span data-ttu-id="6805f-106">in Die Adresse der ersten Methoden Instanz.</span><span class="sxs-lookup"><span data-stu-id="6805f-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="6805f-107">in Die AppDomain der Methoden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="6805f-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="6805f-108">vorgenommen Ein Handle zum Auflisten der Methoden Instanzen.</span><span class="sxs-lookup"><span data-stu-id="6805f-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="6805f-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6805f-109">Remarks</span></span>

<span data-ttu-id="6805f-110">Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 28. Slot der virtuellen Methoden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6805f-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6805f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6805f-111">Requirements</span></span>

<span data-ttu-id="6805f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6805f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6805f-113">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="6805f-113">**Header:** None</span></span>  
<span data-ttu-id="6805f-114">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="6805f-114">**Library:** None</span></span>  
<span data-ttu-id="6805f-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6805f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6805f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6805f-116">See also</span></span>

- [<span data-ttu-id="6805f-117">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6805f-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6805f-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6805f-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="6805f-119">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6805f-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
