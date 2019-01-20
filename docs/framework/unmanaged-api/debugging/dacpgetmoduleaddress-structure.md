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
ms.openlocfilehash: ca9ce04e9a4770d46f88e10785f4dafd044c9212
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416392"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="df69f-102">DacpGetModuleAddress-Struktur</span><span class="sxs-lookup"><span data-stu-id="df69f-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="df69f-103">Definiert den Container für eine Anforderung zum modulimport Adresse an.</span><span class="sxs-lookup"><span data-stu-id="df69f-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="df69f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df69f-104">Syntax</span></span>

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="df69f-105">Member</span><span class="sxs-lookup"><span data-stu-id="df69f-105">Members</span></span>

| <span data-ttu-id="df69f-106">Member</span><span class="sxs-lookup"><span data-stu-id="df69f-106">Member</span></span>      | <span data-ttu-id="df69f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df69f-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="df69f-108">Der Zeiger auf das Modul.</span><span class="sxs-lookup"><span data-stu-id="df69f-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="df69f-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="df69f-109">Methods</span></span>

| <span data-ttu-id="df69f-110">Methode</span><span class="sxs-lookup"><span data-stu-id="df69f-110">Method</span></span>                                                                                               | <span data-ttu-id="df69f-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df69f-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="df69f-112">Anforderung</span><span class="sxs-lookup"><span data-stu-id="df69f-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="df69f-113">Führt eine Anforderung zum Auffüllen der Struktur aus der angegebenen Runtime-Struktur.</span><span class="sxs-lookup"><span data-stu-id="df69f-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="df69f-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df69f-114">Remarks</span></span>

<span data-ttu-id="df69f-115">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="df69f-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="df69f-116">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben, in dem `CLRDATA_ADDRESS` ist eine 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="df69f-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="df69f-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df69f-117">Requirements</span></span>
<span data-ttu-id="df69f-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df69f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="df69f-119">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="df69f-119">**Header:** None</span></span>  
<span data-ttu-id="df69f-120">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="df69f-120">**Library:** None</span></span>  
<span data-ttu-id="df69f-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="df69f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="df69f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df69f-122">See Also</span></span>
- [<span data-ttu-id="df69f-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="df69f-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="df69f-124">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="df69f-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
