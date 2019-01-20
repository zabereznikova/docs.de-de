---
title: IXCLRDataMethodDefinition::EndEnumInstances-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7901ba3ac95052e265df619d06996b4c9ce8baa6
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416400"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="dc0f0-102">IXCLRDataMethodDefinition::EndEnumInstances-Methode</span><span class="sxs-lookup"><span data-stu-id="dc0f0-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="dc0f0-103">Gibt die vom internen Iteratoren, die verwendet werden, während der Instanzenumeration verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="dc0f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc0f0-104">Syntax</span></span>

```
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="dc0f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc0f0-105">Parameters</span></span>

<span data-ttu-id="dc0f0-106">`handle` [out] Ein Handle für das Auflisten der Instanzen.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-106">`handle` [out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc0f0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc0f0-107">Remarks</span></span>

<span data-ttu-id="dc0f0-108">Die angegebene Methode ist Teil der `IXCLRDataMethodDefinition` Schnittstelle, und mit dem fünften Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="dc0f0-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="dc0f0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc0f0-109">Requirements</span></span>

<span data-ttu-id="dc0f0-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc0f0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="dc0f0-111">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="dc0f0-111">**Header:** None</span></span>  
<span data-ttu-id="dc0f0-112">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="dc0f0-112">**Library:** None</span></span>  
<span data-ttu-id="dc0f0-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dc0f0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="dc0f0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc0f0-114">See Also</span></span>

- [<span data-ttu-id="dc0f0-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="dc0f0-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="dc0f0-116">IXCLRDataMethodDefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc0f0-116">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
