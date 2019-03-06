---
title: IXCLRDataProcess::EndEnumModules-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3b7050e92af6fc58b45837840b2796a5deac955c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375336"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="5fea0-102">IXCLRDataProcess::EndEnumModules-Methode</span><span class="sxs-lookup"><span data-stu-id="5fea0-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="5fea0-103">Gibt die Ressourcen, die von internen Iteratoren, die verwendet werden, während der Modul-Enumeration verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fea0-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5fea0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fea0-104">Syntax</span></span>
```
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="5fea0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5fea0-105">Parameters</span></span>

`handle`\
<span data-ttu-id="5fea0-106">[out] Ein Handle für das Auflisten der Module.</span><span class="sxs-lookup"><span data-stu-id="5fea0-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="5fea0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5fea0-107">Remarks</span></span>

<span data-ttu-id="5fea0-108">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 26. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="5fea0-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5fea0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5fea0-109">Requirements</span></span>

<span data-ttu-id="5fea0-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fea0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="5fea0-111">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="5fea0-111">**Header:** None</span></span>   
<span data-ttu-id="5fea0-112">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="5fea0-112">**Library:** None</span></span>   
<span data-ttu-id="5fea0-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5fea0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   

## <a name="see-also"></a><span data-ttu-id="5fea0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fea0-114">See also</span></span>

- [<span data-ttu-id="5fea0-115">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5fea0-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="5fea0-116">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fea0-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
