---
title: 'Ixclrdatamethoddefinition:: startenuminstance-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b0c37c666f23f04239ed827246b87c43ee8d5ad9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420928"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="6bfb1-102">Ixclrdatamethoddefinition:: startenuminstance-Methode</span><span class="sxs-lookup"><span data-stu-id="6bfb1-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="6bfb1-103">Stellt ein Handle für die Enumeration von Methoden Instanzen für einen angegebenen bereit `IXCLRDataAppDomain` .</span><span class="sxs-lookup"><span data-stu-id="6bfb1-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6bfb1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bfb1-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="6bfb1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6bfb1-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="6bfb1-106">in Eine AppDomain für die-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="6bfb1-107">vorgenommen Ein Handle zum Auflisten der-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="6bfb1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6bfb1-108">Remarks</span></span>

<span data-ttu-id="6bfb1-109">Die bereitgestellte Methode ist Teil der `IXCLRDataMethodDefinition` -Schnittstelle und entspricht dem 5. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6bfb1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6bfb1-110">Requirements</span></span>

<span data-ttu-id="6bfb1-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bfb1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6bfb1-112">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="6bfb1-112">**Header:** None</span></span>  
<span data-ttu-id="6bfb1-113">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="6bfb1-113">**Library:** None</span></span>  
<span data-ttu-id="6bfb1-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6bfb1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6bfb1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bfb1-115">See also</span></span>

- [<span data-ttu-id="6bfb1-116">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6bfb1-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6bfb1-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6bfb1-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="6bfb1-118">IXCLRDataMethodDefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6bfb1-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
