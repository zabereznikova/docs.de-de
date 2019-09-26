---
title: Clrdatasourcetype-Enumeration
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7ace405e2624f15b1cdb6d383222ae87c93289bb
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274094"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="90696-102">Clrdatasourcetype-Enumeration</span><span class="sxs-lookup"><span data-stu-id="90696-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="90696-103">Stellt Werte bereit, die von der CLRDATA_IL_ADDRESS_MAP-Struktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="90696-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="90696-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90696-104">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="90696-105">Member</span><span class="sxs-lookup"><span data-stu-id="90696-105">Members</span></span>

| <span data-ttu-id="90696-106">Member</span><span class="sxs-lookup"><span data-stu-id="90696-106">Member</span></span>                        | <span data-ttu-id="90696-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90696-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="90696-108">Um anzugeben, dass nichts anderes gilt.</span><span class="sxs-lookup"><span data-stu-id="90696-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="90696-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90696-109">Remarks</span></span>

<span data-ttu-id="90696-110">Diese Enumeration befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="90696-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="90696-111">Um es zu verwenden, definieren Sie eine Enumeration, wie oben im Code definiert.</span><span class="sxs-lookup"><span data-stu-id="90696-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="90696-112">Dies gilt auch für einen Alias `CLRDATA_ENUM` , wie in [Common Data Types](../common-data-types-unmanaged-api-reference.md)erwähnt.</span><span class="sxs-lookup"><span data-stu-id="90696-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="90696-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90696-113">Requirements</span></span>

<span data-ttu-id="90696-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90696-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="90696-115">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="90696-115">**Header:** None</span></span>  
<span data-ttu-id="90696-116">**Fern** Keine</span><span class="sxs-lookup"><span data-stu-id="90696-116">**Library:** None</span></span>  
<span data-ttu-id="90696-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="90696-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="90696-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90696-118">See also</span></span>

- [<span data-ttu-id="90696-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="90696-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="90696-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="90696-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
