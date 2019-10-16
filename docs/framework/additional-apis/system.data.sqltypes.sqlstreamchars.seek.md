---
title: SqlStreamChars. Seek (Int64, SeekOrigin)-Methode (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: db8aba0a86c140ba62af8056011226532d415951
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395595"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="854c9-102">SqlStreamChars. Seek (Int64, SeekOrigin)-Methode</span><span class="sxs-lookup"><span data-stu-id="854c9-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="854c9-103">Legt beim Überschreiben in einer abgeleiteten Klasse die Position im aktuellen Stream fest.</span><span class="sxs-lookup"><span data-stu-id="854c9-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="854c9-104">Die Assembly, die diese Methode enthält, hat eine Friend-Beziehung mit SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="854c9-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="854c9-105">Sie ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="854c9-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="854c9-106">Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.</span><span class="sxs-lookup"><span data-stu-id="854c9-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="854c9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="854c9-107">Parameters</span></span>

`offset`\
<span data-ttu-id="854c9-108">Ein Byte Offset relativ zu `origin`.</span><span class="sxs-lookup"><span data-stu-id="854c9-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="854c9-109">Einer der Enumerationswerte, der den Bezugspunkt angibt, von dem aus die neue Position abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="854c9-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="854c9-110">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="854c9-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="854c9-111">Die neue Position innerhalb des aktuellen Streams.</span><span class="sxs-lookup"><span data-stu-id="854c9-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="854c9-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="854c9-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="854c9-113">Die `SqlStreamChars.Seek`-Methode ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="854c9-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="854c9-114">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="854c9-114">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="854c9-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="854c9-115">Requirements</span></span>

<span data-ttu-id="854c9-116">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="854c9-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="854c9-117">**Assembly:** System. Data (in "System. Data. dll")</span><span class="sxs-lookup"><span data-stu-id="854c9-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="854c9-118">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="854c9-118">**.NET Framework versions:** Available since 2.0.</span></span>
