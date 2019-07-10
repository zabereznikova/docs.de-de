---
title: CLRDataSourceType-Enumeration
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
ms.openlocfilehash: d26cf45a0243d61757af5d9d0c00cf135ae15bdf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740870"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="8b714-102">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8b714-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="8b714-103">Enthält Werte, die von der Struktur CLRDATA_IL_ADDRESS_MAP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b714-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8b714-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b714-104">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="8b714-105">Member</span><span class="sxs-lookup"><span data-stu-id="8b714-105">Members</span></span>

| <span data-ttu-id="8b714-106">Member</span><span class="sxs-lookup"><span data-stu-id="8b714-106">Member</span></span>                        | <span data-ttu-id="8b714-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b714-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="8b714-108">Um anzugeben, dass nichts angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8b714-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="8b714-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b714-109">Remarks</span></span>

<span data-ttu-id="8b714-110">Diese Enumeration befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="8b714-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8b714-111">Um es zu verwenden, definieren Sie eine Enumeration, wie oben in Ihrem Code definiert.</span><span class="sxs-lookup"><span data-stu-id="8b714-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="8b714-112">Dies ist auch als Alias für `CLRDATA_ENUM` Siehe [allgemeine Datentypen](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8b714-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="8b714-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b714-113">Requirements</span></span>

<span data-ttu-id="8b714-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b714-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8b714-115">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="8b714-115">**Header:** None</span></span>  
<span data-ttu-id="8b714-116">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="8b714-116">**Library:** None</span></span>  
<span data-ttu-id="8b714-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8b714-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8b714-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b714-118">See also</span></span>

- [<span data-ttu-id="8b714-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8b714-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="8b714-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8b714-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
