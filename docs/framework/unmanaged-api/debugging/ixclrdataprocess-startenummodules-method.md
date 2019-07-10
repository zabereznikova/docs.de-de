---
title: IXCLRDataProcess::StartEnumModules-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 79c4e0ed99a068d7d806d5c25580dc477aac6475
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752624"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="4d1ed-102">IXCLRDataProcess::StartEnumModules-Methode</span><span class="sxs-lookup"><span data-stu-id="4d1ed-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="4d1ed-103">Stellt ein Handle zum Auflisten von der Modules eines Prozesses.</span><span class="sxs-lookup"><span data-stu-id="4d1ed-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4d1ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d1ed-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="4d1ed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d1ed-105">Parameters</span></span>

`handle`\
<span data-ttu-id="4d1ed-106">[out] Ein Handle für das Auflisten der Module.</span><span class="sxs-lookup"><span data-stu-id="4d1ed-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="4d1ed-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4d1ed-107">Remarks</span></span>

<span data-ttu-id="4d1ed-108">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 24. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="4d1ed-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4d1ed-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4d1ed-109">Requirements</span></span>

<span data-ttu-id="4d1ed-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d1ed-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4d1ed-111">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="4d1ed-111">**Header:** None</span></span>  
<span data-ttu-id="4d1ed-112">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="4d1ed-112">**Library:** None</span></span>  
<span data-ttu-id="4d1ed-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4d1ed-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4d1ed-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d1ed-114">See also</span></span>

- [<span data-ttu-id="4d1ed-115">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4d1ed-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="4d1ed-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4d1ed-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="4d1ed-117">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d1ed-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
