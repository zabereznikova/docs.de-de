---
title: IXCLRDataModule::GetMethodDefinitionByToken-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1371b86f30324908a639b3b1bbae0ae007ba590a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708089"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="9c9d4-102">IXCLRDataModule::GetMethodDefinitionByToken-Methode</span><span class="sxs-lookup"><span data-stu-id="9c9d4-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="9c9d4-103">Ruft die Definition der Methode für einen angegebenen Metadatentoken ab.</span><span class="sxs-lookup"><span data-stu-id="9c9d4-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9c9d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c9d4-104">Syntax</span></span>

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

### <a name="parameters"></a><span data-ttu-id="9c9d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c9d4-105">Parameters</span></span>

<span data-ttu-id="9c9d4-106">`token` [in] Das Methodentoken.</span><span class="sxs-lookup"><span data-stu-id="9c9d4-106">`token` [in] The method token.</span></span>

<span data-ttu-id="9c9d4-107">`methodDefinition` [out] Die Definition der Methode.</span><span class="sxs-lookup"><span data-stu-id="9c9d4-107">`methodDefinition` [out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c9d4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c9d4-108">Remarks</span></span>

<span data-ttu-id="9c9d4-109">Die angegebene Methode ist Teil der `IXCLRDataModule` Schnittstelle, und mit dem 25. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="9c9d4-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c9d4-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c9d4-110">Requirements</span></span>

<span data-ttu-id="9c9d4-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c9d4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9c9d4-112">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="9c9d4-112">**Header:** None</span></span>  
<span data-ttu-id="9c9d4-113">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="9c9d4-113">**Library:** None</span></span>  
<span data-ttu-id="9c9d4-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9c9d4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="9c9d4-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c9d4-115">See also</span></span>

- [<span data-ttu-id="9c9d4-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9c9d4-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9c9d4-117">IXCLRDataModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c9d4-117">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
