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
ms.openlocfilehash: 752d87c5f4a6b8d854a06be8962ee754cdd4622d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132001"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="1ac32-102">DacpModuleData-Struktur</span><span class="sxs-lookup"><span data-stu-id="1ac32-102">DacpModuleData Structure</span></span>

<span data-ttu-id="1ac32-103">Definiert einen Transport-Puffer für die Runtime-Informationen des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="1ac32-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1ac32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ac32-104">Syntax</span></span>

```
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="1ac32-105">Member</span><span class="sxs-lookup"><span data-stu-id="1ac32-105">Members</span></span>

| <span data-ttu-id="1ac32-106">Member</span><span class="sxs-lookup"><span data-stu-id="1ac32-106">Member</span></span>    | <span data-ttu-id="1ac32-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ac32-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="1ac32-108">Die Adresse des Modulobjekts.</span><span class="sxs-lookup"><span data-stu-id="1ac32-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="1ac32-109">Ein Zeiger auf die Datei (portable Executable)-Datei.</span><span class="sxs-lookup"><span data-stu-id="1ac32-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="1ac32-110">Die Adresse des geladenen Bilds der Basiswert.</span><span class="sxs-lookup"><span data-stu-id="1ac32-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="1ac32-111">Ein Puffer Nutzlast zusätzlicher Module-Informationen, die von der Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ac32-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1ac32-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ac32-112">Remarks</span></span>

<span data-ttu-id="1ac32-113">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="1ac32-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="1ac32-114">Definieren Sie die Struktur wie oben angegeben, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ac32-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ac32-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ac32-115">Requirements</span></span>
<span data-ttu-id="1ac32-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ac32-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1ac32-117">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="1ac32-117">**Header:** None</span></span>  
<span data-ttu-id="1ac32-118">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="1ac32-118">**Library:** None</span></span>  
<span data-ttu-id="1ac32-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1ac32-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1ac32-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ac32-120">See also</span></span>

- [<span data-ttu-id="1ac32-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1ac32-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="1ac32-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="1ac32-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
