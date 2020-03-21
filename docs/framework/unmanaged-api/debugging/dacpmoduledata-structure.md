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
ms.openlocfilehash: c24bdce64eb7e208bf3830940d7beab1ebf92e78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179186"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="68ffb-102">DacpModuleData-Struktur</span><span class="sxs-lookup"><span data-stu-id="68ffb-102">DacpModuleData Structure</span></span>

<span data-ttu-id="68ffb-103">Definiert einen Transportpuffer für die Laufzeitinformationen eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="68ffb-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="68ffb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68ffb-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="68ffb-105">Members</span><span class="sxs-lookup"><span data-stu-id="68ffb-105">Members</span></span>

| <span data-ttu-id="68ffb-106">Member</span><span class="sxs-lookup"><span data-stu-id="68ffb-106">Member</span></span>    | <span data-ttu-id="68ffb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68ffb-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="68ffb-108">Adresse des Modulobjekts.</span><span class="sxs-lookup"><span data-stu-id="68ffb-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="68ffb-109">Ein Zeiger auf die portable ausführbare Datei (PE).</span><span class="sxs-lookup"><span data-stu-id="68ffb-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="68ffb-110">Die Adresse der Basis des geladenen Bildes.</span><span class="sxs-lookup"><span data-stu-id="68ffb-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="68ffb-111">Ein Nutzlastpuffer für zusätzliche Modulinformationen, die von der Laufzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68ffb-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="68ffb-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="68ffb-112">Remarks</span></span>

<span data-ttu-id="68ffb-113">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="68ffb-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="68ffb-114">Um sie zu verwenden, definieren Sie die oben angegebene Struktur.</span><span class="sxs-lookup"><span data-stu-id="68ffb-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="68ffb-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="68ffb-115">Requirements</span></span>
<span data-ttu-id="68ffb-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68ffb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="68ffb-117">**Kopfzeile:** nichts</span><span class="sxs-lookup"><span data-stu-id="68ffb-117">**Header:** None</span></span>  
<span data-ttu-id="68ffb-118">**Bibliothek:** nichts</span><span class="sxs-lookup"><span data-stu-id="68ffb-118">**Library:** None</span></span>  
<span data-ttu-id="68ffb-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="68ffb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="68ffb-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68ffb-120">See also</span></span>

- [<span data-ttu-id="68ffb-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="68ffb-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="68ffb-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="68ffb-122">Debugging Structures</span></span>](debugging-structures.md)
