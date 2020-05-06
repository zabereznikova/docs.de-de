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
ms.openlocfilehash: e460264e2393858c028ba51aec4a4f2c01649994
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860828"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="ed03b-102">DacpGetModuleAddress-Struktur</span><span class="sxs-lookup"><span data-stu-id="ed03b-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="ed03b-103">Definiert den Container für eine Modul Adress Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ed03b-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ed03b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed03b-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="ed03b-105">Members</span><span class="sxs-lookup"><span data-stu-id="ed03b-105">Members</span></span>

| <span data-ttu-id="ed03b-106">Member</span><span class="sxs-lookup"><span data-stu-id="ed03b-106">Member</span></span>      | <span data-ttu-id="ed03b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ed03b-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="ed03b-108">Der Zeiger auf das Modul.</span><span class="sxs-lookup"><span data-stu-id="ed03b-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="ed03b-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="ed03b-109">Methods</span></span>

| <span data-ttu-id="ed03b-110">Methode</span><span class="sxs-lookup"><span data-stu-id="ed03b-110">Method</span></span>                                                                                               | <span data-ttu-id="ed03b-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ed03b-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="ed03b-112">Anforderung</span><span class="sxs-lookup"><span data-stu-id="ed03b-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="ed03b-113">Führt eine Anforderung aus, um die-Struktur aus der angegebenen Laufzeitstruktur aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="ed03b-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ed03b-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed03b-114">Remarks</span></span>

<span data-ttu-id="ed03b-115">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="ed03b-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ed03b-116">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben `CLRDATA_ADDRESS` , wobei eine 64-Bit-Ganzzahl ohne Vorzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="ed03b-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="ed03b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed03b-117">Requirements</span></span>
<span data-ttu-id="ed03b-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed03b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ed03b-119">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="ed03b-119">**Header:** None</span></span>  
<span data-ttu-id="ed03b-120">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="ed03b-120">**Library:** None</span></span>  
<span data-ttu-id="ed03b-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ed03b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ed03b-122">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="ed03b-122">See also</span></span>

- [<span data-ttu-id="ed03b-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ed03b-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="ed03b-124">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="ed03b-124">Debugging Structures</span></span>](debugging-structures.md)
