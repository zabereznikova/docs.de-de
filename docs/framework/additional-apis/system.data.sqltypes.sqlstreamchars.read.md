---
title: SqlStreamChars. Read (Char [], Int32, Int32)-Methode (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9c8a1526e75fdc304022e74a7cc52506762489ea
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395749"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="10e12-102">SqlStreamChars. Read (Char [], Int32, Int32)-Methode</span><span class="sxs-lookup"><span data-stu-id="10e12-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="10e12-103">Liest beim Überschreiben in einer abgeleiteten Klasse die nächsten Zeichensätze aus dem Eingabestream.</span><span class="sxs-lookup"><span data-stu-id="10e12-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="10e12-104">Die Assembly, die diese Methode enthält, hat eine Friend-Beziehung mit SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="10e12-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="10e12-105">Sie ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="10e12-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="10e12-106">Verwenden Sie für andere Datenbanken den von dieser Datenbank bereitgestellten Hostingmechanismus.</span><span class="sxs-lookup"><span data-stu-id="10e12-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="10e12-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="10e12-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="10e12-108">Ein zu lesende Char-Array.</span><span class="sxs-lookup"><span data-stu-id="10e12-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="10e12-109">Ein Offset relativ zum Ursprung.</span><span class="sxs-lookup"><span data-stu-id="10e12-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="10e12-110">Die Anzahl der Zeichen, die aus dem aktuellen Stream gelesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="10e12-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="10e12-111">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="10e12-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="10e12-112">Die Gesamtanzahl der in den Puffer gelesenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="10e12-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="10e12-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10e12-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="10e12-114">Die `SqlStreamChars.Read`-Methode ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10e12-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="10e12-115">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="10e12-115">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="10e12-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10e12-116">Requirements</span></span>

<span data-ttu-id="10e12-117">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="10e12-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="10e12-118">**Assembly:** System. Data (in "System. Data. dll")</span><span class="sxs-lookup"><span data-stu-id="10e12-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="10e12-119">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="10e12-119">**.NET Framework versions:** Available since 2.0.</span></span>
