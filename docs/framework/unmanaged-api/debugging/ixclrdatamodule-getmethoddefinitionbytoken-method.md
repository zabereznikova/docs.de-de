---
title: 'Ixclrdatamodule:: GetMethodDefinitionByToken-Methode'
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
ms.openlocfilehash: c70920205b27376d453bdd0a13223c6a5569075b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395293"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="1328a-102">Ixclrdatamodule:: GetMethodDefinitionByToken-Methode</span><span class="sxs-lookup"><span data-stu-id="1328a-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="1328a-103">Ruft die Methoden Definition ab, die einem angegebenen Metadatentoken entspricht.</span><span class="sxs-lookup"><span data-stu-id="1328a-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1328a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1328a-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="1328a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1328a-105">Parameters</span></span>

`token`\
<span data-ttu-id="1328a-106">in Das Methoden Token.</span><span class="sxs-lookup"><span data-stu-id="1328a-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="1328a-107">vorgenommen Die Methoden Definition.</span><span class="sxs-lookup"><span data-stu-id="1328a-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="1328a-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1328a-108">Remarks</span></span>

<span data-ttu-id="1328a-109">Die bereitgestellte Methode ist Teil der `IXCLRDataModule` -Schnittstelle und entspricht dem 26. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="1328a-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1328a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1328a-110">Requirements</span></span>

<span data-ttu-id="1328a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1328a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1328a-112">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="1328a-112">**Header:** None</span></span>  
<span data-ttu-id="1328a-113">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="1328a-113">**Library:** None</span></span>  
<span data-ttu-id="1328a-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1328a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1328a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1328a-115">See also</span></span>

- [<span data-ttu-id="1328a-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1328a-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="1328a-117">IXCLRDataModule Interface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1328a-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
