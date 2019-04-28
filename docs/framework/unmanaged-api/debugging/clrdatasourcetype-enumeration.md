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
ms.openlocfilehash: c8b3f338659e2784db8deca3e1776e7926c30c32
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609677"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="34ecd-102">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="34ecd-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="34ecd-103">Enthält Werte, die von der Struktur CLRDATA_IL_ADDRESS_MAP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34ecd-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="34ecd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34ecd-104">Syntax</span></span>

```
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="34ecd-105">Member</span><span class="sxs-lookup"><span data-stu-id="34ecd-105">Members</span></span>

| <span data-ttu-id="34ecd-106">Member</span><span class="sxs-lookup"><span data-stu-id="34ecd-106">Member</span></span>                        | <span data-ttu-id="34ecd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34ecd-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="34ecd-108">Um anzugeben, dass nichts angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="34ecd-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="34ecd-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34ecd-109">Remarks</span></span>

<span data-ttu-id="34ecd-110">Diese Enumeration befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="34ecd-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="34ecd-111">Um es zu verwenden, definieren Sie eine Enumeration, wie oben in Ihrem Code definiert.</span><span class="sxs-lookup"><span data-stu-id="34ecd-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="34ecd-112">Dies ist auch als Alias für `CLRDATA_ENUM` Siehe [allgemeine Datentypen](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="34ecd-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="34ecd-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34ecd-113">Requirements</span></span>

<span data-ttu-id="34ecd-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34ecd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="34ecd-115">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="34ecd-115">**Header:** None</span></span>  
<span data-ttu-id="34ecd-116">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="34ecd-116">**Library:** None</span></span>  
<span data-ttu-id="34ecd-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="34ecd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="34ecd-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34ecd-118">See also</span></span>

- [<span data-ttu-id="34ecd-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="34ecd-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="34ecd-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="34ecd-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
