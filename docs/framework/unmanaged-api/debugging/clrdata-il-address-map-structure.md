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
ms.openlocfilehash: 3aac7e24fa9cd03350aebf5f441063bcedfaed04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644767"
---
# <a name="clrdatailaddressmap-structure"></a><span data-ttu-id="ce33c-102">CLRDATA_IL_ADDRESS_MAP-Struktur</span><span class="sxs-lookup"><span data-stu-id="ce33c-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="ce33c-103">Definiert eine IL-Adresszuordnung an.</span><span class="sxs-lookup"><span data-stu-id="ce33c-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ce33c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce33c-104">Syntax</span></span>

```
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="ce33c-105">Member</span><span class="sxs-lookup"><span data-stu-id="ce33c-105">Members</span></span>

| <span data-ttu-id="ce33c-106">Member</span><span class="sxs-lookup"><span data-stu-id="ce33c-106">Member</span></span>         | <span data-ttu-id="ce33c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce33c-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="ce33c-108">IL-Offset für den eigenständigen-Adressbereich</span><span class="sxs-lookup"><span data-stu-id="ce33c-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="ce33c-109">Die Startadresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="ce33c-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="ce33c-110">Die letzte Adresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="ce33c-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="ce33c-111">Der Typ der Daten.</span><span class="sxs-lookup"><span data-stu-id="ce33c-111">The type of the data.</span></span> <span data-ttu-id="ce33c-112">Dieser Wert wird derzeit nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce33c-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="ce33c-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce33c-113">Remarks</span></span>

<span data-ttu-id="ce33c-114">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="ce33c-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ce33c-115">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben, in dem `CLRDATA_ADDRESS` ist eine 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="ce33c-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="ce33c-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce33c-116">Requirements</span></span>

<span data-ttu-id="ce33c-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce33c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ce33c-118">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="ce33c-118">**Header:** None</span></span>  
<span data-ttu-id="ce33c-119">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="ce33c-119">**Library:** None</span></span>   
<span data-ttu-id="ce33c-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ce33c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ce33c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce33c-121">See also</span></span>

- [<span data-ttu-id="ce33c-122">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ce33c-122">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="ce33c-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ce33c-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ce33c-124">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="ce33c-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
