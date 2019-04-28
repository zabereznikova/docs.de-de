---
title: SqlStreamChars.Read (Char [], Int32, Int32)-Methode (System.Data.SqlTypes)
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
ms.openlocfilehash: df92acfd4050eb16d3a101b20b9b44560273f4d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675233"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="74a0b-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span><span class="sxs-lookup"><span data-stu-id="74a0b-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="74a0b-103">Ruft beim Überschreiben in einer abgeleiteten Klasse liest Sie die nächste Gruppe von Zeichen aus dem Eingabestream.</span><span class="sxs-lookup"><span data-stu-id="74a0b-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="74a0b-104">Die Assembly mit dieser Methode hat eine Friend-Beziehung SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="74a0b-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="74a0b-105">Es ist für die Verwendung durch SQL Server vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="74a0b-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="74a0b-106">Verwenden Sie für andere Datenbanken Hostingmechanismus, die von dieser Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="74a0b-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="74a0b-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="74a0b-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="74a0b-108">Ein Char-Array gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="74a0b-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="74a0b-109">Ein Offset relativ zum Ursprung.</span><span class="sxs-lookup"><span data-stu-id="74a0b-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="74a0b-110">Die Anzahl der Zeichen aus dem aktuellen Stream gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="74a0b-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="74a0b-111">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="74a0b-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="74a0b-112">Die Gesamtanzahl der in den Puffer gelesenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="74a0b-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="74a0b-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74a0b-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="74a0b-114">Die `SqlStreamChars.Read` Methode privat ist und nicht direkt in Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="74a0b-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="74a0b-115">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="74a0b-115">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="74a0b-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74a0b-116">Requirements</span></span>

<span data-ttu-id="74a0b-117">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="74a0b-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="74a0b-118">**Assembly:** System.Data (in "System.Data.dll")</span><span class="sxs-lookup"><span data-stu-id="74a0b-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="74a0b-119">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="74a0b-119">**.NET Framework versions:** Available since 2.0.</span></span>