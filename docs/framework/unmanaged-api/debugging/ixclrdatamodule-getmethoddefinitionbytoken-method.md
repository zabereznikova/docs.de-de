---
title: IXCLRDataModule::GetMethodDefinitionbyToken-Methode
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
ms.openlocfilehash: 294c5340caf2217f9337d654a11a63a43d46febd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176668"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="ff632-102">IXCLRDataModule::GetMethodDefinitionbyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="ff632-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="ff632-103">Ruft die Methodendefinition ab, die einem bestimmten Metadatentoken entspricht.</span><span class="sxs-lookup"><span data-stu-id="ff632-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ff632-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff632-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="ff632-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff632-105">Parameters</span></span>

`token`\
<span data-ttu-id="ff632-106">[in] Das Methodentoken.</span><span class="sxs-lookup"><span data-stu-id="ff632-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="ff632-107">[out] Die Methodendefinition.</span><span class="sxs-lookup"><span data-stu-id="ff632-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff632-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ff632-108">Remarks</span></span>

<span data-ttu-id="ff632-109">Die bereitgestellte Methode `IXCLRDataModule` ist Teil der Schnittstelle und entspricht dem 25. Steckplatz der virtuellen Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="ff632-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff632-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ff632-110">Requirements</span></span>

<span data-ttu-id="ff632-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff632-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ff632-112">**Kopfzeile:** nichts</span><span class="sxs-lookup"><span data-stu-id="ff632-112">**Header:** None</span></span>  
<span data-ttu-id="ff632-113">**Bibliothek:** nichts</span><span class="sxs-lookup"><span data-stu-id="ff632-113">**Library:** None</span></span>  
<span data-ttu-id="ff632-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ff632-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ff632-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff632-115">See also</span></span>

- [<span data-ttu-id="ff632-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ff632-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="ff632-117">IXCLRDataModule Interface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff632-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
