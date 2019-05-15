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
ms.openlocfilehash: 4cc4266f569c3fb3e70227ec2543b962f7bd4b1d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632046"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="4a1c9-102">ISOSDacInterface::GetModuleData-Methode</span><span class="sxs-lookup"><span data-stu-id="4a1c9-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="4a1c9-103">Die Daten, die für das Modul geladen, die an einer bestimmten Adresse abruft.</span><span class="sxs-lookup"><span data-stu-id="4a1c9-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4a1c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a1c9-104">Syntax</span></span>

```
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="4a1c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a1c9-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="4a1c9-106">[in] Die Adresse des Moduls zum Abrufen von Informationen für.</span><span class="sxs-lookup"><span data-stu-id="4a1c9-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="4a1c9-107">[out] Die [DacpModuleData Struktur](dacpmoduledata-structure.md) , die die Informationen des geladenen Moduls enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="4a1c9-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a1c9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a1c9-108">Remarks</span></span>

<span data-ttu-id="4a1c9-109">Die angegebene Methode ist Teil der `ISOSDacInterface` Schnittstelle, und mit dem 13. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="4a1c9-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 13th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4a1c9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4a1c9-110">Requirements</span></span>

<span data-ttu-id="4a1c9-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a1c9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4a1c9-112">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="4a1c9-112">**Header:** None</span></span>  
<span data-ttu-id="4a1c9-113">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="4a1c9-113">**Library:** None</span></span>  
<span data-ttu-id="4a1c9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4a1c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4a1c9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a1c9-115">See also</span></span>

- [<span data-ttu-id="4a1c9-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4a1c9-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="4a1c9-117">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a1c9-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
