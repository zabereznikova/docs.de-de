---
title: ISOSDacInterface::GetModuleData-Methode
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: ed151f998ed7d28ba7ae170839ce2fa3a1ee6135
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490449"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="00ccc-102">ISOSDacInterface::GetModuleData-Methode</span><span class="sxs-lookup"><span data-stu-id="00ccc-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="00ccc-103">Die Daten, die für das Modul geladen, die an einer bestimmten Adresse abruft.</span><span class="sxs-lookup"><span data-stu-id="00ccc-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="00ccc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00ccc-104">Syntax</span></span>

```
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="00ccc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00ccc-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="00ccc-106">[in] Die Adresse des Moduls zum Abrufen von Informationen für.</span><span class="sxs-lookup"><span data-stu-id="00ccc-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="00ccc-107">[out] Die [DacpModuleData Struktur](dacpmoduledata-structure.md) , die die Informationen des geladenen Moduls enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="00ccc-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>


## <a name="remarks"></a><span data-ttu-id="00ccc-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00ccc-108">Remarks</span></span>

<span data-ttu-id="00ccc-109">Die angegebene Methode ist Teil der `ISOSDacInterface` Schnittstelle, und mit dem 13. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="00ccc-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 13th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="00ccc-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00ccc-110">Requirements</span></span>

<span data-ttu-id="00ccc-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00ccc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="00ccc-112">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="00ccc-112">**Header:** None</span></span>  
<span data-ttu-id="00ccc-113">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="00ccc-113">**Library:** None</span></span>  
<span data-ttu-id="00ccc-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="00ccc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="00ccc-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00ccc-115">See also</span></span>

- [<span data-ttu-id="00ccc-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="00ccc-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="00ccc-117">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00ccc-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)