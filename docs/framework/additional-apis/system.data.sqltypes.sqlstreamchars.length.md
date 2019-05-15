---
title: SqlStreamChars.Length-Eigenschaft (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 8f318f593237dc555d546858152bb03546c8306b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634453"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="9052b-102">SqlStreamChars.Length-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9052b-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="9052b-103">Ruft beim Überschreiben in einer abgeleiteten Klasse ruft die Länge des aktuellen Streams ab.</span><span class="sxs-lookup"><span data-stu-id="9052b-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="9052b-104">Die Assembly, die diese Eigenschaft enthält, verfügt über eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="9052b-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="9052b-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9052b-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="9052b-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9052b-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="9052b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9052b-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="9052b-108">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="9052b-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="9052b-109">Die Länge des Streams.</span><span class="sxs-lookup"><span data-stu-id="9052b-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="9052b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9052b-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="9052b-111">Die `SqlStreamChars.Length` -Eigenschaft ist privat und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9052b-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="9052b-112">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="9052b-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="9052b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9052b-113">Requirements</span></span>

<span data-ttu-id="9052b-114">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="9052b-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="9052b-115">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="9052b-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="9052b-116">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="9052b-116">**.NET Framework versions:** Available since 2.0.</span></span>
