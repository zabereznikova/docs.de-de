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
ms.openlocfilehash: 0de622e96b9138b86cfc77c51d1a215c1868accf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375921"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="8e120-102">IXCLRDataProcess::StartEnumModules-Methode</span><span class="sxs-lookup"><span data-stu-id="8e120-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="8e120-103">Stellt ein Handle zum Auflisten von der Modules eines Prozesses.</span><span class="sxs-lookup"><span data-stu-id="8e120-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8e120-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e120-104">Syntax</span></span>

```
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

### <a name="parameters"></a><span data-ttu-id="8e120-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8e120-105">Parameters</span></span>

`handle`\
<span data-ttu-id="8e120-106">[out] Ein Handle für das Auflisten der Module.</span><span class="sxs-lookup"><span data-stu-id="8e120-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e120-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e120-107">Remarks</span></span>

<span data-ttu-id="8e120-108">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 24. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="8e120-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e120-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e120-109">Requirements</span></span>

<span data-ttu-id="8e120-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e120-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8e120-111">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="8e120-111">**Header:** None</span></span>  
<span data-ttu-id="8e120-112">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="8e120-112">**Library:** None</span></span>  
<span data-ttu-id="8e120-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8e120-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8e120-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e120-114">See also</span></span>

- [<span data-ttu-id="8e120-115">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8e120-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="8e120-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8e120-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="8e120-117">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e120-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
