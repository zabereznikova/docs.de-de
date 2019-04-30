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
ms.openlocfilehash: 484ca79483fc4a5d8f0d1cf2cd5a961c297249e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961304"
---
# <a name="clrdataaddressrange-structure"></a><span data-ttu-id="93893-102">CLRDATA_ADDRESS_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="93893-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="93893-103">Definiert einen Adressbereich an.</span><span class="sxs-lookup"><span data-stu-id="93893-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="93893-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93893-104">Syntax</span></span>

```
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="93893-105">Member</span><span class="sxs-lookup"><span data-stu-id="93893-105">Members</span></span>

| <span data-ttu-id="93893-106">Member</span><span class="sxs-lookup"><span data-stu-id="93893-106">Member</span></span>         | <span data-ttu-id="93893-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93893-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="93893-108">Die Startadresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="93893-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="93893-109">Die letzte Adresse des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="93893-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="93893-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93893-110">Remarks</span></span>

<span data-ttu-id="93893-111">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="93893-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="93893-112">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben, in dem `CLRDATA_ADDRESS` ist eine 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="93893-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="93893-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="93893-113">Requirements</span></span>

<span data-ttu-id="93893-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93893-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="93893-115">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="93893-115">**Header:** None</span></span>  
<span data-ttu-id="93893-116">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="93893-116">**Library:** None</span></span>  
<span data-ttu-id="93893-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="93893-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="93893-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93893-118">See also</span></span>

- [<span data-ttu-id="93893-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="93893-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="93893-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="93893-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
