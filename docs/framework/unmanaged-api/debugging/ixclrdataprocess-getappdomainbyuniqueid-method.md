---
title: IXCLRDataProcess::GetAppDomainByUniqueId Method
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 83e7d4e1a4ff3c2e6f573d6c097c7cdb9c5f3c54
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416471"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="404ed-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span><span class="sxs-lookup"><span data-stu-id="404ed-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="404ed-103">Ruft eine `AppDomain` in einem Prozess, der auf Grundlage seines eindeutigen Bezeichners.</span><span class="sxs-lookup"><span data-stu-id="404ed-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="404ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="404ed-104">Syntax</span></span>
```
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

### <a name="parameters"></a><span data-ttu-id="404ed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="404ed-105">Parameters</span></span>
<span data-ttu-id="404ed-106">`id` [in] Der eindeutige Bezeichner der Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="404ed-106">`id` [in] The unique identifier of the AppDomain</span></span>

<span data-ttu-id="404ed-107">`appDomain` [out] Der AppDomain</span><span class="sxs-lookup"><span data-stu-id="404ed-107">`appDomain` [out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="404ed-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="404ed-108">Remarks</span></span>

<span data-ttu-id="404ed-109">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle und zum 20. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="404ed-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="404ed-110">Die `IXCLRDataAppDomain*` zurückgegeben, die für die Interaktion mit anderen APIs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="404ed-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="404ed-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="404ed-111">Requirements</span></span>
<span data-ttu-id="404ed-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="404ed-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="404ed-113">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="404ed-113">**Header:** None</span></span>  
<span data-ttu-id="404ed-114">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="404ed-114">**Library:** None</span></span>  
<span data-ttu-id="404ed-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="404ed-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="404ed-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="404ed-116">See Also</span></span>
- [<span data-ttu-id="404ed-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="404ed-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="404ed-118">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="404ed-118">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
