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
ms.openlocfilehash: 727005437289b4bc66ab90f280b80a79f4db06db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775496"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="549a1-102">IXCLRDataModule::GetMethodDefinitionByToken-Methode</span><span class="sxs-lookup"><span data-stu-id="549a1-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="549a1-103">Ruft die Definition der Methode für einen angegebenen Metadatentoken ab.</span><span class="sxs-lookup"><span data-stu-id="549a1-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="549a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="549a1-104">Syntax</span></span>

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="549a1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="549a1-105">Parameters</span></span>

`token`\
<span data-ttu-id="549a1-106">[in] Das Methodentoken.</span><span class="sxs-lookup"><span data-stu-id="549a1-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="549a1-107">[out] Die Definition der Methode.</span><span class="sxs-lookup"><span data-stu-id="549a1-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="549a1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="549a1-108">Remarks</span></span>

<span data-ttu-id="549a1-109">Die angegebene Methode ist Teil der `IXCLRDataModule` Schnittstelle, und mit dem 25. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="549a1-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="549a1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="549a1-110">Requirements</span></span>

<span data-ttu-id="549a1-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="549a1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="549a1-112">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="549a1-112">**Header:** None</span></span>  
<span data-ttu-id="549a1-113">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="549a1-113">**Library:** None</span></span>  
<span data-ttu-id="549a1-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="549a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="549a1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="549a1-115">See also</span></span>

- [<span data-ttu-id="549a1-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="549a1-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="549a1-117">IXCLRDataModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="549a1-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
