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
ms.openlocfilehash: 3f6928832d822422177ebd7def142422953468a0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274290"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="7c3ca-102">CLRDATA_IL_ADDRESS_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="7c3ca-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="7c3ca-103">Definiert eine Il-to-Address-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="7c3ca-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7c3ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c3ca-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="7c3ca-105">Member</span><span class="sxs-lookup"><span data-stu-id="7c3ca-105">Members</span></span>

| <span data-ttu-id="7c3ca-106">Member</span><span class="sxs-lookup"><span data-stu-id="7c3ca-106">Member</span></span>         | <span data-ttu-id="7c3ca-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c3ca-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="7c3ca-108">IL-Offset für den enthaltenen Adressbereich</span><span class="sxs-lookup"><span data-stu-id="7c3ca-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="7c3ca-109">Die Startadresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="7c3ca-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="7c3ca-110">Die Endadresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="7c3ca-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="7c3ca-111">Der Typ der Daten.</span><span class="sxs-lookup"><span data-stu-id="7c3ca-111">The type of the data.</span></span> <span data-ttu-id="7c3ca-112">Dieser Wert wird derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c3ca-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="7c3ca-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c3ca-113">Remarks</span></span>

<span data-ttu-id="7c3ca-114">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="7c3ca-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="7c3ca-115">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben `CLRDATA_ADDRESS` , wobei eine 64-Bit-Ganzzahl ohne Vorzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="7c3ca-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="7c3ca-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c3ca-116">Requirements</span></span>

<span data-ttu-id="7c3ca-117">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c3ca-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7c3ca-118">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="7c3ca-118">**Header:** None</span></span>  
<span data-ttu-id="7c3ca-119">**Fern** Keine</span><span class="sxs-lookup"><span data-stu-id="7c3ca-119">**Library:** None</span></span>   
<span data-ttu-id="7c3ca-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7c3ca-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7c3ca-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c3ca-121">See also</span></span>

- [<span data-ttu-id="7c3ca-122">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7c3ca-122">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="7c3ca-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7c3ca-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="7c3ca-124">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="7c3ca-124">Debugging Structures</span></span>](debugging-structures.md)
