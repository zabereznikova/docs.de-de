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
ms.openlocfilehash: 2e27082ba4c35bc10eb65139b2af6c81c10d79a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739125"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="6f861-102">DacpModuleData-Struktur</span><span class="sxs-lookup"><span data-stu-id="6f861-102">DacpModuleData Structure</span></span>

<span data-ttu-id="6f861-103">Definiert einen Transport-Puffer für die Runtime-Informationen des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="6f861-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6f861-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f861-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="6f861-105">Member</span><span class="sxs-lookup"><span data-stu-id="6f861-105">Members</span></span>

| <span data-ttu-id="6f861-106">Member</span><span class="sxs-lookup"><span data-stu-id="6f861-106">Member</span></span>    | <span data-ttu-id="6f861-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f861-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="6f861-108">Die Adresse des Modulobjekts.</span><span class="sxs-lookup"><span data-stu-id="6f861-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="6f861-109">Ein Zeiger auf die Datei (portable Executable)-Datei.</span><span class="sxs-lookup"><span data-stu-id="6f861-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="6f861-110">Die Adresse des geladenen Bilds der Basiswert.</span><span class="sxs-lookup"><span data-stu-id="6f861-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="6f861-111">Ein Puffer Nutzlast zusätzlicher Module-Informationen, die von der Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6f861-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="6f861-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f861-112">Remarks</span></span>

<span data-ttu-id="6f861-113">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="6f861-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="6f861-114">Definieren Sie die Struktur wie oben angegeben, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f861-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="6f861-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f861-115">Requirements</span></span>
<span data-ttu-id="6f861-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f861-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6f861-117">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="6f861-117">**Header:** None</span></span>  
<span data-ttu-id="6f861-118">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="6f861-118">**Library:** None</span></span>  
<span data-ttu-id="6f861-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6f861-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6f861-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f861-120">See also</span></span>

- [<span data-ttu-id="6f861-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6f861-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6f861-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="6f861-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
