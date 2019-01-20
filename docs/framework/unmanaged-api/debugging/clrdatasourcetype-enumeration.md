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
ms.openlocfilehash: 36651de5053e994103f79c9021e8e18e126f91fa
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416385"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="9ba6d-102">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9ba6d-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="9ba6d-103">Enthält Werte, die von der Struktur CLRDATA_IL_ADDRESS_MAP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ba6d-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9ba6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ba6d-104">Syntax</span></span>

```
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="9ba6d-105">Member</span><span class="sxs-lookup"><span data-stu-id="9ba6d-105">Members</span></span>

| <span data-ttu-id="9ba6d-106">Member</span><span class="sxs-lookup"><span data-stu-id="9ba6d-106">Member</span></span>                        | <span data-ttu-id="9ba6d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ba6d-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="9ba6d-108">Um anzugeben, dass nichts angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ba6d-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="9ba6d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ba6d-109">Remarks</span></span>

<span data-ttu-id="9ba6d-110">Diese Enumeration befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="9ba6d-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9ba6d-111">Um es zu verwenden, definieren Sie eine Enumeration, wie oben in Ihrem Code definiert.</span><span class="sxs-lookup"><span data-stu-id="9ba6d-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="9ba6d-112">Dies ist auch als Alias für `CLRDATA_ENUM` Siehe [allgemeine Datentypen](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="9ba6d-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="9ba6d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ba6d-113">Requirements</span></span>

<span data-ttu-id="9ba6d-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ba6d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9ba6d-115">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="9ba6d-115">**Header:** None</span></span>  
<span data-ttu-id="9ba6d-116">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="9ba6d-116">**Library:** None</span></span>  
<span data-ttu-id="9ba6d-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9ba6d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9ba6d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ba6d-118">See Also</span></span>

- [<span data-ttu-id="9ba6d-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9ba6d-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9ba6d-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9ba6d-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
