---
title: SqlStreamChars.CanSeek-Eigenschaft (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
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
ms.openlocfilehash: 8d7bd7fb90177932b413c379f618a6d36374de57
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54223142"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="7cd5f-102">SqlStreamChars.CanSeek-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7cd5f-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="7cd5f-103">Ruft beim Überschreiben in einer abgeleiteten Klasse ruft einen Wert, der angibt, ob der aktuelle Stream Suchvorgänge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7cd5f-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="7cd5f-104">Die Assembly, die diese Eigenschaft enthält, verfügt über eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="7cd5f-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="7cd5f-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="7cd5f-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="7cd5f-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7cd5f-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="7cd5f-107">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="7cd5f-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="7cd5f-108">`true` Wenn der aktuelle Stream Suchvorgänge unterstützt; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="7cd5f-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7cd5f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cd5f-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="7cd5f-110">Die `SqlStreamChars.CanSeek` -Eigenschaft ist privat und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7cd5f-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="7cd5f-111">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="7cd5f-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7cd5f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7cd5f-112">Requirements</span></span>

<span data-ttu-id="7cd5f-113">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="7cd5f-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="7cd5f-114">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="7cd5f-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="7cd5f-115">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="7cd5f-115">**.NET Framework versions:** Available since 2.0.</span></span>