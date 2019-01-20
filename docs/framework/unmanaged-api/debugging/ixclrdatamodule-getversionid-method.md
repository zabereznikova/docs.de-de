---
title: IXCLRDataModule::GetVersionId-Methode
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
ms.openlocfilehash: ac4111abdf6a471aca1eca72a86e33698debbff6
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416401"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="5c1d7-102">IXCLRDataModule::GetVersionId-Methode</span><span class="sxs-lookup"><span data-stu-id="5c1d7-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="5c1d7-103">Ruft die Versions-ID des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="5c1d7-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5c1d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c1d7-104">Syntax</span></span>

```
HRESULT GetVersionId(
    [out] GUID* vid
);
```

### <a name="parameters"></a><span data-ttu-id="5c1d7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5c1d7-105">Parameters</span></span>

<span data-ttu-id="5c1d7-106">`vid` [out] Versions-ID des Moduls.</span><span class="sxs-lookup"><span data-stu-id="5c1d7-106">`vid` [out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c1d7-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c1d7-107">Remarks</span></span>

<span data-ttu-id="5c1d7-108">Die angegebene Methode ist Teil der `IXCLRDataModule` Schnittstelle, und mit dem 40. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="5c1d7-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5c1d7-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c1d7-109">Requirements</span></span>

<span data-ttu-id="5c1d7-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c1d7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5c1d7-111">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="5c1d7-111">**Header:** None</span></span>  
<span data-ttu-id="5c1d7-112">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="5c1d7-112">**Library:** None</span></span>  
<span data-ttu-id="5c1d7-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5c1d7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5c1d7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c1d7-114">See Also</span></span>

- [<span data-ttu-id="5c1d7-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5c1d7-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="5c1d7-116">IXCLRDataModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5c1d7-116">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
