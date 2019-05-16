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
ms.openlocfilehash: 6ec18bcf079c7687df4ac9b7c5db23b84383c517
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632296"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="65404-102">IXCLRDataModule::GetVersionId-Methode</span><span class="sxs-lookup"><span data-stu-id="65404-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="65404-103">Ruft die Versions-ID des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="65404-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="65404-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65404-104">Syntax</span></span>

```
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="65404-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65404-105">Parameters</span></span>

`vid`\
<span data-ttu-id="65404-106">[out] Versions-ID des Moduls.</span><span class="sxs-lookup"><span data-stu-id="65404-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="65404-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65404-107">Remarks</span></span>

<span data-ttu-id="65404-108">Die angegebene Methode ist Teil der `IXCLRDataModule` Schnittstelle, und mit dem 40. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="65404-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="65404-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65404-109">Requirements</span></span>

<span data-ttu-id="65404-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65404-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="65404-111">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="65404-111">**Header:** None</span></span>  
<span data-ttu-id="65404-112">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="65404-112">**Library:** None</span></span>  
<span data-ttu-id="65404-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="65404-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="65404-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65404-114">See also</span></span>

- [<span data-ttu-id="65404-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="65404-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="65404-116">IXCLRDataModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65404-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
