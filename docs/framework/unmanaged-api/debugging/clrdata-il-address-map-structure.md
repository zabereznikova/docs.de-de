---
title: CLRDATA_IL_ADDRESS_MAP-Struktur
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 94ebef007cf2893b63383aa4657d382728d3c759
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416393"
---
# <a name="clrdatailaddressmap-structure"></a><span data-ttu-id="0efcb-102">CLRDATA_IL_ADDRESS_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="0efcb-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="0efcb-103">Definiert eine IL-Adresszuordnung an.</span><span class="sxs-lookup"><span data-stu-id="0efcb-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0efcb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0efcb-104">Syntax</span></span>

```
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="0efcb-105">Member</span><span class="sxs-lookup"><span data-stu-id="0efcb-105">Members</span></span>

| <span data-ttu-id="0efcb-106">Member</span><span class="sxs-lookup"><span data-stu-id="0efcb-106">Member</span></span>         | <span data-ttu-id="0efcb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0efcb-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="0efcb-108">IL-Offset für den eigenständigen-Adressbereich</span><span class="sxs-lookup"><span data-stu-id="0efcb-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="0efcb-109">Die Startadresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="0efcb-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="0efcb-110">Die letzte Adresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="0efcb-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="0efcb-111">Der Typ der Daten.</span><span class="sxs-lookup"><span data-stu-id="0efcb-111">The type of the data.</span></span> <span data-ttu-id="0efcb-112">Dieser Wert wird derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0efcb-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="0efcb-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0efcb-113">Remarks</span></span>

<span data-ttu-id="0efcb-114">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="0efcb-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0efcb-115">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben, in dem `CLRDATA_ADDRESS` ist eine 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="0efcb-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="0efcb-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0efcb-116">Requirements</span></span>

<span data-ttu-id="0efcb-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0efcb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0efcb-118">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="0efcb-118">**Header:** None</span></span>  
<span data-ttu-id="0efcb-119">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="0efcb-119">**Library:** None</span></span>   
<span data-ttu-id="0efcb-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0efcb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0efcb-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0efcb-121">See Also</span></span>

- [<span data-ttu-id="0efcb-122">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0efcb-122">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="0efcb-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="0efcb-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="0efcb-124">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="0efcb-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
