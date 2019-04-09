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
ms.openlocfilehash: 257fa2cf03a62ea888b76519aa5c9f9e84038045
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126502"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="71c37-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span><span class="sxs-lookup"><span data-stu-id="71c37-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="71c37-103">Ruft eine `AppDomain` in einem Prozess, der auf Grundlage seines eindeutigen Bezeichners.</span><span class="sxs-lookup"><span data-stu-id="71c37-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="71c37-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71c37-104">Syntax</span></span>
```
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="71c37-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71c37-105">Parameters</span></span>

`id`\
<span data-ttu-id="71c37-106">[in] Der eindeutige Bezeichner der Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="71c37-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="71c37-107">[out] Der AppDomain</span><span class="sxs-lookup"><span data-stu-id="71c37-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="71c37-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71c37-108">Remarks</span></span>

<span data-ttu-id="71c37-109">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle und zum 20. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="71c37-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="71c37-110">Die `IXCLRDataAppDomain*` zurückgegeben, die für die Interaktion mit anderen APIs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="71c37-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="71c37-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71c37-111">Requirements</span></span>
<span data-ttu-id="71c37-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71c37-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="71c37-113">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="71c37-113">**Header:** None</span></span>  
<span data-ttu-id="71c37-114">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="71c37-114">**Library:** None</span></span>  
**<span data-ttu-id="71c37-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="71c37-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="71c37-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71c37-116">See also</span></span>

- [<span data-ttu-id="71c37-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="71c37-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="71c37-118">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71c37-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
