---
title: SqlStreamChars. length-Eigenschaft (System. Data. SqlTypes)
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
ms.openlocfilehash: 2171b10d1c0eb7bcad894cc44c5103bdab18b0a5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395604"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="521aa-102">SqlStreamChars. length (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="521aa-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="521aa-103">Ruft beim Überschreiben in einer abgeleiteten Klasse die Länge des aktuellen Streams ab.</span><span class="sxs-lookup"><span data-stu-id="521aa-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="521aa-104">Die Assembly, die diese Eigenschaft enthält, hat eine Friend-Beziehung mit SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="521aa-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="521aa-105">Sie ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="521aa-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="521aa-106">Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.</span><span class="sxs-lookup"><span data-stu-id="521aa-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="521aa-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="521aa-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="521aa-108">Eigenschafts Wert</span><span class="sxs-lookup"><span data-stu-id="521aa-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="521aa-109">Die Länge des Streams.</span><span class="sxs-lookup"><span data-stu-id="521aa-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="521aa-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="521aa-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="521aa-111">Die `SqlStreamChars.Length`-Eigenschaft ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="521aa-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="521aa-112">Microsoft unterstützt die Verwendung dieser Eigenschaft in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="521aa-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="521aa-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="521aa-113">Requirements</span></span>

<span data-ttu-id="521aa-114">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="521aa-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="521aa-115">**Assembly:** System. Data (in "System. Data. dll")</span><span class="sxs-lookup"><span data-stu-id="521aa-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="521aa-116">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="521aa-116">**.NET Framework versions:** Available since 2.0.</span></span>
