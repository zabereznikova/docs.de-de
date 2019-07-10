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
ms.openlocfilehash: 2f34ae3e6687027aeb75e7ea169487fc8cbda466
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741031"
---
# <a name="clrdatailaddressmap-structure"></a><span data-ttu-id="1bc44-102">CLRDATA_IL_ADDRESS_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="1bc44-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="1bc44-103">Definiert eine IL-Adresszuordnung an.</span><span class="sxs-lookup"><span data-stu-id="1bc44-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1bc44-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1bc44-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="1bc44-105">Member</span><span class="sxs-lookup"><span data-stu-id="1bc44-105">Members</span></span>

| <span data-ttu-id="1bc44-106">Member</span><span class="sxs-lookup"><span data-stu-id="1bc44-106">Member</span></span>         | <span data-ttu-id="1bc44-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1bc44-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="1bc44-108">IL-Offset für den eigenständigen-Adressbereich</span><span class="sxs-lookup"><span data-stu-id="1bc44-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="1bc44-109">Die Startadresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="1bc44-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="1bc44-110">Die letzte Adresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="1bc44-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="1bc44-111">Der Typ der Daten.</span><span class="sxs-lookup"><span data-stu-id="1bc44-111">The type of the data.</span></span> <span data-ttu-id="1bc44-112">Dieser Wert wird derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="1bc44-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="1bc44-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1bc44-113">Remarks</span></span>

<span data-ttu-id="1bc44-114">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="1bc44-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="1bc44-115">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben, in dem `CLRDATA_ADDRESS` ist eine 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="1bc44-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="1bc44-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1bc44-116">Requirements</span></span>

<span data-ttu-id="1bc44-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bc44-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1bc44-118">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="1bc44-118">**Header:** None</span></span>  
<span data-ttu-id="1bc44-119">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="1bc44-119">**Library:** None</span></span>   
<span data-ttu-id="1bc44-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1bc44-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1bc44-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1bc44-121">See also</span></span>

- [<span data-ttu-id="1bc44-122">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1bc44-122">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="1bc44-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1bc44-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="1bc44-124">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="1bc44-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
