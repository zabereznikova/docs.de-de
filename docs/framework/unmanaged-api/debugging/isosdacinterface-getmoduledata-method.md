---
title: 'Isosdacinterface:: getmoduledata-Methode'
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
ms.openlocfilehash: b302100eb6cbfa83896cd358762c496ea01f7509
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420980"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="8e8a3-102">Isosdacinterface:: getmoduledata-Methode</span><span class="sxs-lookup"><span data-stu-id="8e8a3-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="8e8a3-103">Ruft die Daten ab, die dem Modul entsprechen, das an einer bestimmten Adresse geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="8e8a3-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8e8a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e8a3-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="8e8a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8e8a3-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="8e8a3-106">in Die Adresse des Moduls, für das Informationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8e8a3-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="8e8a3-107">vorgenommen Die [dacpmoduledata-Struktur](dacpmoduledata-structure.md) , die die Informationen des geladenen Moduls enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="8e8a3-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e8a3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e8a3-108">Remarks</span></span>

<span data-ttu-id="8e8a3-109">Die bereitgestellte Methode ist Teil der `ISOSDacInterface` -Schnittstelle und entspricht dem 14. Slot der Tabelle der virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="8e8a3-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e8a3-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e8a3-110">Requirements</span></span>

<span data-ttu-id="8e8a3-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e8a3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8e8a3-112">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="8e8a3-112">**Header:** None</span></span>  
<span data-ttu-id="8e8a3-113">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="8e8a3-113">**Library:** None</span></span>  
<span data-ttu-id="8e8a3-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8e8a3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8e8a3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e8a3-115">See also</span></span>

- [<span data-ttu-id="8e8a3-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8e8a3-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="8e8a3-117">ISOSDacInterface-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e8a3-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
