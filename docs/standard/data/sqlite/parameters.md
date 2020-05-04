---
title: Parameter
ms.date: 12/13/2019
description: Hier erfahren Sie mehr über die Verwendung von SQL-Parametern.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401202"
---
# <a name="parameters"></a><span data-ttu-id="9fdfa-103">Parameter</span><span class="sxs-lookup"><span data-stu-id="9fdfa-103">Parameters</span></span>

<span data-ttu-id="9fdfa-104">Parameter werden zum Schutz vor Angriffen durch Einschleusung von SQL-Befehlen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="9fdfa-105">Anstatt Benutzereingaben mit SQL-Anweisungen zu verketten, stellen Sie mithilfe von Parametern sicher, dass Eingaben nur als Literalwert behandelt und nie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="9fdfa-106">In SQLite sind Parameter in der Regel überall dort zulässig, wo in SQL-Anweisungen Literalwerte zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="9fdfa-107">Parametern können die Präfixe `:`, `@` oder `$` vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="9fdfa-108">Weitere Informationen zur Zuordnung von .NET-Werten zu SQLite-Werten finden Sie unter [Datentypen](types.md).</span><span class="sxs-lookup"><span data-stu-id="9fdfa-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="9fdfa-109">Abschneiden</span><span class="sxs-lookup"><span data-stu-id="9fdfa-109">Truncation</span></span>

<span data-ttu-id="9fdfa-110">Verwenden Sie zum Abschneiden von TEXT- und BLOB-Werten die Eigenschaft <xref:Microsoft.Data.Sqlite.SqliteParameter.Size>.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="9fdfa-111">Alternative Typen</span><span class="sxs-lookup"><span data-stu-id="9fdfa-111">Alternative types</span></span>

<span data-ttu-id="9fdfa-112">Möglicherweise sollten Sie ab und zu einen alternativen SQLite-Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="9fdfa-113">Legen Sie dazu die Eigenschaft <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> fest.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="9fdfa-114">Die folgende Zuordnung von alternativen Datentypen ist hierbei nützlich.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="9fdfa-115">Die Standardzuordnungen finden Sie unter [Datentypen](types.md).</span><span class="sxs-lookup"><span data-stu-id="9fdfa-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="9fdfa-116">Wert</span><span class="sxs-lookup"><span data-stu-id="9fdfa-116">Value</span></span>          | <span data-ttu-id="9fdfa-117">SQLite-Typ</span><span class="sxs-lookup"><span data-stu-id="9fdfa-117">SqliteType</span></span> | <span data-ttu-id="9fdfa-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9fdfa-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="9fdfa-119">Char</span><span class="sxs-lookup"><span data-stu-id="9fdfa-119">Char</span></span>           | <span data-ttu-id="9fdfa-120">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="9fdfa-120">Integer</span></span>    | <span data-ttu-id="9fdfa-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="9fdfa-121">UTF-16</span></span>           |
| <span data-ttu-id="9fdfa-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="9fdfa-122">DateTime</span></span>       | <span data-ttu-id="9fdfa-123">Real</span><span class="sxs-lookup"><span data-stu-id="9fdfa-123">Real</span></span>       | <span data-ttu-id="9fdfa-124">Wert für julianisches Datum</span><span class="sxs-lookup"><span data-stu-id="9fdfa-124">Julian day value</span></span> |
| <span data-ttu-id="9fdfa-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9fdfa-125">DateTimeOffset</span></span> | <span data-ttu-id="9fdfa-126">Real</span><span class="sxs-lookup"><span data-stu-id="9fdfa-126">Real</span></span>       | <span data-ttu-id="9fdfa-127">Wert für julianisches Datum</span><span class="sxs-lookup"><span data-stu-id="9fdfa-127">Julian day value</span></span> |
| <span data-ttu-id="9fdfa-128">GUID</span><span class="sxs-lookup"><span data-stu-id="9fdfa-128">Guid</span></span>           | <span data-ttu-id="9fdfa-129">Blob</span><span class="sxs-lookup"><span data-stu-id="9fdfa-129">Blob</span></span>       |                  |
| <span data-ttu-id="9fdfa-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="9fdfa-130">TimeSpan</span></span>       | <span data-ttu-id="9fdfa-131">Real</span><span class="sxs-lookup"><span data-stu-id="9fdfa-131">Real</span></span>       | <span data-ttu-id="9fdfa-132">In Tagen</span><span class="sxs-lookup"><span data-stu-id="9fdfa-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="9fdfa-133">Ausgabeparameter</span><span class="sxs-lookup"><span data-stu-id="9fdfa-133">Output parameters</span></span>

<span data-ttu-id="9fdfa-134">Ausgabeparameter werden von SQLite nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="9fdfa-135">Geben Sie stattdessen Werte in den Abfrageergebnissen zurück.</span><span class="sxs-lookup"><span data-stu-id="9fdfa-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fdfa-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fdfa-136">See also</span></span>

* [<span data-ttu-id="9fdfa-137">Datentypen</span><span class="sxs-lookup"><span data-stu-id="9fdfa-137">Data types</span></span>](types.md)
