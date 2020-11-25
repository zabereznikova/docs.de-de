---
title: DacpModuleData-Struktur
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 5d27ba2de9ff6ed184b6ddf50a517d0dae7715f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723050"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="fbf5e-102">DacpModuleData-Struktur</span><span class="sxs-lookup"><span data-stu-id="fbf5e-102">DacpModuleData Structure</span></span>

<span data-ttu-id="fbf5e-103">Definiert einen Transport Puffer für die Laufzeitinformationen eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="fbf5e-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fbf5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbf5e-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="fbf5e-105">Member</span><span class="sxs-lookup"><span data-stu-id="fbf5e-105">Members</span></span>

| <span data-ttu-id="fbf5e-106">Member</span><span class="sxs-lookup"><span data-stu-id="fbf5e-106">Member</span></span>    | <span data-ttu-id="fbf5e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fbf5e-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="fbf5e-108">Adresse des Modul Objekts.</span><span class="sxs-lookup"><span data-stu-id="fbf5e-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="fbf5e-109">Ein Zeiger auf die portable ausführbare Datei (PE).</span><span class="sxs-lookup"><span data-stu-id="fbf5e-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="fbf5e-110">Die Adresse der Basis des geladenen Bilds.</span><span class="sxs-lookup"><span data-stu-id="fbf5e-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="fbf5e-111">Ein Nutz Last Puffer für zusätzliche Modul Informationen, die von der Laufzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbf5e-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="fbf5e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fbf5e-112">Remarks</span></span>

<span data-ttu-id="fbf5e-113">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="fbf5e-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="fbf5e-114">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben.</span><span class="sxs-lookup"><span data-stu-id="fbf5e-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="fbf5e-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fbf5e-115">Requirements</span></span>

<span data-ttu-id="fbf5e-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbf5e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fbf5e-117">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="fbf5e-117">**Header:** None</span></span>  
<span data-ttu-id="fbf5e-118">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="fbf5e-118">**Library:** None</span></span>  
<span data-ttu-id="fbf5e-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fbf5e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fbf5e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fbf5e-120">See also</span></span>

- [<span data-ttu-id="fbf5e-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fbf5e-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="fbf5e-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="fbf5e-122">Debugging Structures</span></span>](debugging-structures.md)
