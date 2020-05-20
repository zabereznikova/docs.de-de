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
ms.openlocfilehash: 9d5ef137a5d76c3d7545ab16921352123e978fb1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420863"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="8a2b2-102">Ixclrdatamodule:: getversionid-Methode</span><span class="sxs-lookup"><span data-stu-id="8a2b2-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="8a2b2-103">Ruft den Versions Bezeichner des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="8a2b2-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8a2b2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a2b2-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="8a2b2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a2b2-105">Parameters</span></span>

`vid`\
<span data-ttu-id="8a2b2-106">vorgenommen Der Versions Bezeichner des Moduls.</span><span class="sxs-lookup"><span data-stu-id="8a2b2-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a2b2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a2b2-107">Remarks</span></span>

<span data-ttu-id="8a2b2-108">Die bereitgestellte Methode ist Teil der `IXCLRDataModule` -Schnittstelle und entspricht dem 41. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="8a2b2-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="8a2b2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a2b2-109">Requirements</span></span>

<span data-ttu-id="8a2b2-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a2b2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8a2b2-111">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="8a2b2-111">**Header:** None</span></span>  
<span data-ttu-id="8a2b2-112">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="8a2b2-112">**Library:** None</span></span>  
<span data-ttu-id="8a2b2-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8a2b2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8a2b2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a2b2-114">See also</span></span>

- [<span data-ttu-id="8a2b2-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8a2b2-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="8a2b2-116">IXCLRDataModule Interface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a2b2-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
