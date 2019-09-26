---
title: CLRDATA_ADDRESS_RANGE-Struktur
ms.date: 01/16/2019
api.name:
- CLRDATA_ADDRESS_RANGE Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_ADDRESS_RANGE Structure
helpviewer.keywords:
- CLRDATA_ADDRESS_RANGE Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 8eb841b4c4f06a3932805ae6222bdd693def5ea0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274311"
---
# <a name="clrdata_address_range-structure"></a><span data-ttu-id="5e817-102">CLRDATA_ADDRESS_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="5e817-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="5e817-103">Definiert einen Adressbereich.</span><span class="sxs-lookup"><span data-stu-id="5e817-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5e817-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e817-104">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="5e817-105">Member</span><span class="sxs-lookup"><span data-stu-id="5e817-105">Members</span></span>

| <span data-ttu-id="5e817-106">Member</span><span class="sxs-lookup"><span data-stu-id="5e817-106">Member</span></span>         | <span data-ttu-id="5e817-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e817-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="5e817-108">Die Startadresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="5e817-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="5e817-109">Die Endadresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="5e817-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="5e817-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e817-110">Remarks</span></span>

<span data-ttu-id="5e817-111">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="5e817-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="5e817-112">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben `CLRDATA_ADDRESS` , wobei eine 64-Bit-Ganzzahl ohne Vorzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="5e817-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e817-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e817-113">Requirements</span></span>

<span data-ttu-id="5e817-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e817-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5e817-115">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="5e817-115">**Header:** None</span></span>  
<span data-ttu-id="5e817-116">**Fern** Keine</span><span class="sxs-lookup"><span data-stu-id="5e817-116">**Library:** None</span></span>  
<span data-ttu-id="5e817-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5e817-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5e817-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e817-118">See also</span></span>

- [<span data-ttu-id="5e817-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5e817-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="5e817-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="5e817-120">Debugging Structures</span></span>](debugging-structures.md)
