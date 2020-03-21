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
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179374"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="2913e-102">CLRDATA_IL_ADDRESS_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="2913e-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="2913e-103">Definiert eine IL-zu-Adresszuordnung.</span><span class="sxs-lookup"><span data-stu-id="2913e-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2913e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2913e-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="2913e-105">Members</span><span class="sxs-lookup"><span data-stu-id="2913e-105">Members</span></span>

| <span data-ttu-id="2913e-106">Member</span><span class="sxs-lookup"><span data-stu-id="2913e-106">Member</span></span>         | <span data-ttu-id="2913e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2913e-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="2913e-108">IL-Offset für den enthaltenen Adressbereich</span><span class="sxs-lookup"><span data-stu-id="2913e-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="2913e-109">Die Startadresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="2913e-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="2913e-110">Die Endadresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="2913e-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="2913e-111">Der Typ der Daten.</span><span class="sxs-lookup"><span data-stu-id="2913e-111">The type of the data.</span></span> <span data-ttu-id="2913e-112">Dieser Wert wird derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2913e-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="2913e-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2913e-113">Remarks</span></span>

<span data-ttu-id="2913e-114">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="2913e-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="2913e-115">Um sie zu verwenden, definieren Sie `CLRDATA_ADDRESS` die oben angegebene Struktur, wobei es sich um eine 64-Bit-Ganzzahl ohne Vorzeichen handelt.</span><span class="sxs-lookup"><span data-stu-id="2913e-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="2913e-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2913e-116">Requirements</span></span>

<span data-ttu-id="2913e-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2913e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2913e-118">**Kopfzeile:** nichts</span><span class="sxs-lookup"><span data-stu-id="2913e-118">**Header:** None</span></span>  
<span data-ttu-id="2913e-119">**Bibliothek:** Keine **.NET Framework-Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2913e-119">**Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2913e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2913e-120">See also</span></span>

- [<span data-ttu-id="2913e-121">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="2913e-121">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="2913e-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2913e-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="2913e-123">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="2913e-123">Debugging Structures</span></span>](debugging-structures.md)
