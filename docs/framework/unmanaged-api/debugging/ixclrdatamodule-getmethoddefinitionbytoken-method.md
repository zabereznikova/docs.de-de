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
ms.openlocfilehash: 2c0cf56f108396226b7c7399f6da75e5f47d36f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744669"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="d9e69-102">IXCLRDataModule::GetMethodDefinitionByToken-Methode</span><span class="sxs-lookup"><span data-stu-id="d9e69-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="d9e69-103">Ruft die Definition der Methode für einen angegebenen Metadatentoken ab.</span><span class="sxs-lookup"><span data-stu-id="d9e69-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d9e69-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9e69-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="d9e69-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9e69-105">Parameters</span></span>

`token`\
<span data-ttu-id="d9e69-106">[in] Das Methodentoken.</span><span class="sxs-lookup"><span data-stu-id="d9e69-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="d9e69-107">[out] Die Definition der Methode.</span><span class="sxs-lookup"><span data-stu-id="d9e69-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9e69-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9e69-108">Remarks</span></span>

<span data-ttu-id="d9e69-109">Die angegebene Methode ist Teil der `IXCLRDataModule` Schnittstelle, und mit dem 25. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="d9e69-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="d9e69-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9e69-110">Requirements</span></span>

<span data-ttu-id="d9e69-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9e69-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d9e69-112">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="d9e69-112">**Header:** None</span></span>  
<span data-ttu-id="d9e69-113">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="d9e69-113">**Library:** None</span></span>  
<span data-ttu-id="d9e69-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e69-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="d9e69-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9e69-115">See also</span></span>

- [<span data-ttu-id="d9e69-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d9e69-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="d9e69-117">IXCLRDataModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9e69-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
