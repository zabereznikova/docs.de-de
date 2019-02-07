---
title: SqlStreamChars.CanSeek-Eigenschaft (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: bde4764af9d0160997dc202f722a12393cfa59c1
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826849"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="faaaa-102">SqlStreamChars.CanSeek-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="faaaa-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="faaaa-103">Ruft beim Überschreiben in einer abgeleiteten Klasse ruft einen Wert, der angibt, ob der aktuelle Stream Suchvorgänge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="faaaa-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="faaaa-104">Die Assembly, die diese Eigenschaft enthält, verfügt über eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="faaaa-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="faaaa-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="faaaa-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="faaaa-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="faaaa-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="faaaa-107">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="faaaa-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="faaaa-108">`true` Wenn der aktuelle Stream Suchvorgänge unterstützt; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="faaaa-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="faaaa-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="faaaa-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="faaaa-110">Die `SqlStreamChars.CanSeek` -Eigenschaft ist privat und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="faaaa-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="faaaa-111">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="faaaa-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="faaaa-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="faaaa-112">Requirements</span></span>

<span data-ttu-id="faaaa-113">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="faaaa-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="faaaa-114">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="faaaa-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="faaaa-115">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="faaaa-115">**.NET Framework versions:** Available since 2.0.</span></span>