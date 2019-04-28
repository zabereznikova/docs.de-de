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
ms.openlocfilehash: 28cd15a793d303e1d6e64c52c1d0095e8d619c7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789700"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="66101-102">IXCLRDataMethodDefinition::EndEnumInstances-Methode</span><span class="sxs-lookup"><span data-stu-id="66101-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="66101-103">Gibt die vom internen Iteratoren, die verwendet werden, während der Instanzenumeration verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="66101-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="66101-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66101-104">Syntax</span></span>

```
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="66101-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="66101-105">Parameters</span></span>

`handle`\
<span data-ttu-id="66101-106">[out] Ein Handle für das Auflisten der Instanzen.</span><span class="sxs-lookup"><span data-stu-id="66101-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="66101-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66101-107">Remarks</span></span>

<span data-ttu-id="66101-108">Die angegebene Methode ist Teil der `IXCLRDataMethodDefinition` Schnittstelle, und mit dem fünften Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="66101-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="66101-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66101-109">Requirements</span></span>

<span data-ttu-id="66101-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66101-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="66101-111">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="66101-111">**Header:** None</span></span>  
<span data-ttu-id="66101-112">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="66101-112">**Library:** None</span></span>  
<span data-ttu-id="66101-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="66101-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="66101-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66101-114">See also</span></span>

- [<span data-ttu-id="66101-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="66101-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="66101-116">IXCLRDataMethodDefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66101-116">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
