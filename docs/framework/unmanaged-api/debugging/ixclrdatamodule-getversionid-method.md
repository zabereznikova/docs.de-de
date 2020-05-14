---
title: 'Ixclrdatamodule:: getversionid-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetVersionId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetVersionId Method
helpviewer.keywords:
- IXCLRDataModule::GetVersionId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ff8ccf42d1131fb15d7473ae12ecefde9d55177f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395277"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="4da72-102">Ixclrdatamodule:: getversionid-Methode</span><span class="sxs-lookup"><span data-stu-id="4da72-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="4da72-103">Ruft den Versions Bezeichner des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="4da72-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4da72-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4da72-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="4da72-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4da72-105">Parameters</span></span>

`vid`\
<span data-ttu-id="4da72-106">vorgenommen Der Versions Bezeichner des Moduls.</span><span class="sxs-lookup"><span data-stu-id="4da72-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="4da72-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4da72-107">Remarks</span></span>

<span data-ttu-id="4da72-108">Die bereitgestellte Methode ist Teil der `IXCLRDataModule` -Schnittstelle und entspricht dem 41. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="4da72-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4da72-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4da72-109">Requirements</span></span>

<span data-ttu-id="4da72-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4da72-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4da72-111">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="4da72-111">**Header:** None</span></span>  
<span data-ttu-id="4da72-112">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="4da72-112">**Library:** None</span></span>  
<span data-ttu-id="4da72-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4da72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4da72-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4da72-114">See also</span></span>

- [<span data-ttu-id="4da72-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4da72-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="4da72-116">IXCLRDataModule Interface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4da72-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
