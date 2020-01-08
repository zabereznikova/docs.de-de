---
title: Parameters
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie SQL-Parameter verwenden.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450423"
---
# <a name="parameters"></a><span data-ttu-id="8dca8-103">Parameters</span><span class="sxs-lookup"><span data-stu-id="8dca8-103">Parameters</span></span>

<span data-ttu-id="8dca8-104">Parameter werden zum Schutz vor Einschleusung von SQL-Befehlen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8dca8-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="8dca8-105">Anstatt Benutzereingaben mit SQL-Anweisungen zu verketten, verwenden Sie Parameter, um sicherzustellen, dass die Eingabe nur als Literalwert behandelt und nie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8dca8-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="8dca8-106">In SQLite sind Parameter in der Regel überall zulässig, wo ein Literalwert in SQL-Anweisungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="8dca8-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="8dca8-107">Parametern kann entweder `:`, `@`oder `$`vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8dca8-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="8dca8-108">Ausführliche Informationen dazu, wie .net-Werte SQLite-Werten zugeordnet werden, finden Sie unter [Datentypen](types.md) .</span><span class="sxs-lookup"><span data-stu-id="8dca8-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="8dca8-109">Abschneiden</span><span class="sxs-lookup"><span data-stu-id="8dca8-109">Truncation</span></span>

<span data-ttu-id="8dca8-110">Verwenden Sie die <xref:Microsoft.Data.Sqlite.SqliteParameter.Size>-Eigenschaft, um Text-und BLOB-Werte abzuschneiden.</span><span class="sxs-lookup"><span data-stu-id="8dca8-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="8dca8-111">Alternative Typen</span><span class="sxs-lookup"><span data-stu-id="8dca8-111">Alternative types</span></span>

<span data-ttu-id="8dca8-112">Manchmal möchten Sie möglicherweise einen alternativen SQLite-Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="8dca8-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="8dca8-113">Legen Sie hierzu die <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="8dca8-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="8dca8-114">Die folgenden alternativen Typmappings können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8dca8-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="8dca8-115">Die Standard Zuordnungen finden Sie unter [Datentypen](types.md).</span><span class="sxs-lookup"><span data-stu-id="8dca8-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="8dca8-116">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="8dca8-116">Value</span></span>          | <span data-ttu-id="8dca8-117">Sqlitetype</span><span class="sxs-lookup"><span data-stu-id="8dca8-117">SqliteType</span></span> | <span data-ttu-id="8dca8-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8dca8-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="8dca8-119">Char</span><span class="sxs-lookup"><span data-stu-id="8dca8-119">Char</span></span>           | <span data-ttu-id="8dca8-120">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="8dca8-120">Integer</span></span>    | <span data-ttu-id="8dca8-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="8dca8-121">UTF-16</span></span>           |
| <span data-ttu-id="8dca8-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="8dca8-122">DateTime</span></span>       | <span data-ttu-id="8dca8-123">Real</span><span class="sxs-lookup"><span data-stu-id="8dca8-123">Real</span></span>       | <span data-ttu-id="8dca8-124">Wert des Julianischen Tags</span><span class="sxs-lookup"><span data-stu-id="8dca8-124">Julian day value</span></span> |
| <span data-ttu-id="8dca8-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8dca8-125">DateTimeOffset</span></span> | <span data-ttu-id="8dca8-126">Real</span><span class="sxs-lookup"><span data-stu-id="8dca8-126">Real</span></span>       | <span data-ttu-id="8dca8-127">Wert des Julianischen Tags</span><span class="sxs-lookup"><span data-stu-id="8dca8-127">Julian day value</span></span> |
| <span data-ttu-id="8dca8-128">GUID</span><span class="sxs-lookup"><span data-stu-id="8dca8-128">Guid</span></span>           | <span data-ttu-id="8dca8-129">Blob</span><span class="sxs-lookup"><span data-stu-id="8dca8-129">Blob</span></span>       |                  |
| <span data-ttu-id="8dca8-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="8dca8-130">TimeSpan</span></span>       | <span data-ttu-id="8dca8-131">Real</span><span class="sxs-lookup"><span data-stu-id="8dca8-131">Real</span></span>       | <span data-ttu-id="8dca8-132">In Tagen</span><span class="sxs-lookup"><span data-stu-id="8dca8-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="8dca8-133">Ausgabeparameter</span><span class="sxs-lookup"><span data-stu-id="8dca8-133">Output parameters</span></span>

<span data-ttu-id="8dca8-134">SQLite unterstützt keine Ausgabeparameter.</span><span class="sxs-lookup"><span data-stu-id="8dca8-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="8dca8-135">Geben Sie stattdessen Werte in den Abfrage Ergebnissen zurück.</span><span class="sxs-lookup"><span data-stu-id="8dca8-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="8dca8-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8dca8-136">See also</span></span>

* [<span data-ttu-id="8dca8-137">Datentypen</span><span class="sxs-lookup"><span data-stu-id="8dca8-137">Data types</span></span>](types.md)
