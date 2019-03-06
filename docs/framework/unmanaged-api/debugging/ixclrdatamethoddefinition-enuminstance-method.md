---
title: IXCLRDataMethodDefinition::EnumInstance-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: dacf76582916ad50f51ae7c8818b496f31f9553e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353113"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="b00d4-102">IXCLRDataMethodDefinition::EnumInstance-Methode</span><span class="sxs-lookup"><span data-stu-id="b00d4-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="b00d4-103">Listet die Instanzen dieser Definition der Methode.</span><span class="sxs-lookup"><span data-stu-id="b00d4-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b00d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b00d4-104">Syntax</span></span>

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="b00d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b00d4-105">Parameters</span></span>

`handle`\
<span data-ttu-id="b00d4-106">[in, out] Ein Handle für das Auflisten der Instanzen.</span><span class="sxs-lookup"><span data-stu-id="b00d4-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="b00d4-107">[out] Die aufgelisteten Instanz.</span><span class="sxs-lookup"><span data-stu-id="b00d4-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="b00d4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b00d4-108">Remarks</span></span>

<span data-ttu-id="b00d4-109">Die angegebene Methode ist Teil der `IXCLRDataMethodDefinition` Schnittstelle, und mit dem vierten Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="b00d4-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b00d4-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b00d4-110">Requirements</span></span>

<span data-ttu-id="b00d4-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b00d4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b00d4-112">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="b00d4-112">**Header:** None</span></span>  
<span data-ttu-id="b00d4-113">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="b00d4-113">**Library:** None</span></span>  
<span data-ttu-id="b00d4-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b00d4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b00d4-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b00d4-115">See also</span></span>

- [<span data-ttu-id="b00d4-116">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b00d4-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b00d4-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b00d4-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b00d4-118">IXCLRDataMethodDefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b00d4-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="b00d4-119">IXCLRDataMethodInstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b00d4-119">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
