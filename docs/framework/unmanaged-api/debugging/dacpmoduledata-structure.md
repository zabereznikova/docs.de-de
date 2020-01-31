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
ms.openlocfilehash: b46a04d67f59c5031b5bd195cef4cc2275e1e5e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793809"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="a19ed-102">DacpModuleData-Struktur</span><span class="sxs-lookup"><span data-stu-id="a19ed-102">DacpModuleData Structure</span></span>

<span data-ttu-id="a19ed-103">Definiert einen Transport Puffer für die Laufzeitinformationen eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="a19ed-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a19ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a19ed-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="a19ed-105">Member</span><span class="sxs-lookup"><span data-stu-id="a19ed-105">Members</span></span>

| <span data-ttu-id="a19ed-106">Member</span><span class="sxs-lookup"><span data-stu-id="a19ed-106">Member</span></span>    | <span data-ttu-id="a19ed-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a19ed-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="a19ed-108">Adresse des Modul Objekts.</span><span class="sxs-lookup"><span data-stu-id="a19ed-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="a19ed-109">Ein Zeiger auf die portable ausführbare Datei (PE).</span><span class="sxs-lookup"><span data-stu-id="a19ed-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="a19ed-110">Die Adresse der Basis des geladenen Bilds.</span><span class="sxs-lookup"><span data-stu-id="a19ed-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="a19ed-111">Ein Nutz Last Puffer für zusätzliche Modul Informationen, die von der Laufzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a19ed-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a19ed-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a19ed-112">Remarks</span></span>

<span data-ttu-id="a19ed-113">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="a19ed-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a19ed-114">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben.</span><span class="sxs-lookup"><span data-stu-id="a19ed-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="a19ed-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a19ed-115">Requirements</span></span>
<span data-ttu-id="a19ed-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a19ed-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a19ed-117">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="a19ed-117">**Header:** None</span></span>  
<span data-ttu-id="a19ed-118">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="a19ed-118">**Library:** None</span></span>  
<span data-ttu-id="a19ed-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a19ed-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a19ed-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a19ed-120">See also</span></span>

- [<span data-ttu-id="a19ed-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a19ed-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="a19ed-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="a19ed-122">Debugging Structures</span></span>](debugging-structures.md)
