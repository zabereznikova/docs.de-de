---
title: SqlChars.Stream-Eigenschaft (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d756b78a7cdbc12562e474ca3d2c9a1f3529f6bf
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54223051"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="ef4c8-102">SqlChars.Stream-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ef4c8-102">SqlChars.Stream Property</span></span>

<span data-ttu-id="ef4c8-103">Übernimmt oder bestimmt den Zeichenstrom.</span><span class="sxs-lookup"><span data-stu-id="ef4c8-103">Gets or sets the character stream.</span></span> <span data-ttu-id="ef4c8-104">Die Assembly, die diese Eigenschaft enthält, verfügt über eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="ef4c8-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="ef4c8-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ef4c8-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="ef4c8-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ef4c8-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="ef4c8-107">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="ef4c8-107">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="ef4c8-108">Der Zeichenstream.</span><span class="sxs-lookup"><span data-stu-id="ef4c8-108">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef4c8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef4c8-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ef4c8-110">Die `SqlChars.Stream` -Eigenschaft ist intern und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef4c8-110">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ef4c8-111">Microsoft unterstützt nicht die Verwendung dieser Eigenschaft in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="ef4c8-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ef4c8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef4c8-112">Requirements</span></span>

<span data-ttu-id="ef4c8-113">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="ef4c8-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="ef4c8-114">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="ef4c8-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="ef4c8-115">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="ef4c8-115">**.NET Framework versions:** Available since 2.0.</span></span>