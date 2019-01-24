---
title: DacpGetModuleAddress-Struktur
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c0a12ab638adfccfb6406aa495bd3568911ee969
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619778"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="8f41d-102">DacpGetModuleAddress-Struktur</span><span class="sxs-lookup"><span data-stu-id="8f41d-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="8f41d-103">Definiert den Container für eine Anforderung zum modulimport Adresse an.</span><span class="sxs-lookup"><span data-stu-id="8f41d-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8f41d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f41d-104">Syntax</span></span>

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="8f41d-105">Member</span><span class="sxs-lookup"><span data-stu-id="8f41d-105">Members</span></span>

| <span data-ttu-id="8f41d-106">Member</span><span class="sxs-lookup"><span data-stu-id="8f41d-106">Member</span></span>      | <span data-ttu-id="8f41d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f41d-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="8f41d-108">Der Zeiger auf das Modul.</span><span class="sxs-lookup"><span data-stu-id="8f41d-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="8f41d-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="8f41d-109">Methods</span></span>

| <span data-ttu-id="8f41d-110">Methode</span><span class="sxs-lookup"><span data-stu-id="8f41d-110">Method</span></span>                                                                                               | <span data-ttu-id="8f41d-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f41d-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="8f41d-112">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8f41d-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="8f41d-113">Führt eine Anforderung zum Auffüllen der Struktur aus der angegebenen Runtime-Struktur.</span><span class="sxs-lookup"><span data-stu-id="8f41d-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8f41d-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f41d-114">Remarks</span></span>

<span data-ttu-id="8f41d-115">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="8f41d-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8f41d-116">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben, in dem `CLRDATA_ADDRESS` ist eine 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="8f41d-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f41d-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f41d-117">Requirements</span></span>
<span data-ttu-id="8f41d-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f41d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8f41d-119">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="8f41d-119">**Header:** None</span></span>  
<span data-ttu-id="8f41d-120">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="8f41d-120">**Library:** None</span></span>  
<span data-ttu-id="8f41d-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8f41d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8f41d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f41d-122">See also</span></span>
- [<span data-ttu-id="8f41d-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8f41d-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="8f41d-124">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="8f41d-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
