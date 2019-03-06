---
title: IXCLRDataMethodDefinition::StartEnumInstances-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e92eea9677731756bdbfcbdcfac1531861fb5dce
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361342"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="51567-102">IXCLRDataMethodDefinition::StartEnumInstances-Methode</span><span class="sxs-lookup"><span data-stu-id="51567-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="51567-103">Stellt ein Handle für die Enumeration der Methodeninstanzen für einen bestimmten `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="51567-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="51567-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51567-104">Syntax</span></span>

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="51567-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="51567-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="51567-106">[in] Eine Anwendungsdomäne für die Enumeration.</span><span class="sxs-lookup"><span data-stu-id="51567-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="51567-107">[out] Ein Handle für das Auflisten der Instanzen.</span><span class="sxs-lookup"><span data-stu-id="51567-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="51567-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51567-108">Remarks</span></span>

<span data-ttu-id="51567-109">Die angegebene Methode ist Teil der `IXCLRDataMethodDefinition` Schnittstelle, und im dritten Einschubfach von der Tabelle virtueller Methoden entspricht.</span><span class="sxs-lookup"><span data-stu-id="51567-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the third slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="51567-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51567-110">Requirements</span></span>

<span data-ttu-id="51567-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51567-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="51567-112">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="51567-112">**Header:** None</span></span>  
<span data-ttu-id="51567-113">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="51567-113">**Library:** None</span></span>  
<span data-ttu-id="51567-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="51567-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="51567-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51567-115">See also</span></span>

- [<span data-ttu-id="51567-116">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="51567-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="51567-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="51567-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="51567-118">IXCLRDataMethodDefinition-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51567-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)