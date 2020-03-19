---
title: Parameter
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie SQL-Parameter verwenden.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401202"
---
# <a name="parameters"></a><span data-ttu-id="faa2d-103">Parameter</span><span class="sxs-lookup"><span data-stu-id="faa2d-103">Parameters</span></span>

<span data-ttu-id="faa2d-104">Parameter werden zum Schutz vor SQL-Injektionsangriffen verwendet.</span><span class="sxs-lookup"><span data-stu-id="faa2d-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="faa2d-105">Anstatt Benutzereingaben mit SQL-Anweisungen zu verketten, verwenden Sie Parameter, um sicherzustellen, dass Die Eingabe immer nur als Literalwert behandelt und nie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="faa2d-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="faa2d-106">In SQLite sind Parameter in der Regel überall dort zulässig, wo ein Literal in SQL-Anweisungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="faa2d-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="faa2d-107">Parametern kann entweder `:`, `@`oder `$`vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="faa2d-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="faa2d-108">Weitere Informationen dazu, wie .NET-Werte SQLite-Werten zugeordnet werden, finden Sie unter [Datentypen.](types.md)</span><span class="sxs-lookup"><span data-stu-id="faa2d-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="faa2d-109">Abschneiden</span><span class="sxs-lookup"><span data-stu-id="faa2d-109">Truncation</span></span>

<span data-ttu-id="faa2d-110">Verwenden <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> Sie die Eigenschaft, um TEXT- und BLOB-Werte abzurunden.</span><span class="sxs-lookup"><span data-stu-id="faa2d-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="faa2d-111">Alternative Typen</span><span class="sxs-lookup"><span data-stu-id="faa2d-111">Alternative types</span></span>

<span data-ttu-id="faa2d-112">Manchmal möchten Sie möglicherweise einen alternativen SQLite-Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="faa2d-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="faa2d-113">Geben Sie hierzu die <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="faa2d-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="faa2d-114">Die folgenden alternativen Typzuordnungen können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="faa2d-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="faa2d-115">Informationen zu den Standardzuordnungen finden Sie unter [Datentypen](types.md).</span><span class="sxs-lookup"><span data-stu-id="faa2d-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="faa2d-116">value</span><span class="sxs-lookup"><span data-stu-id="faa2d-116">Value</span></span>          | <span data-ttu-id="faa2d-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="faa2d-117">SqliteType</span></span> | <span data-ttu-id="faa2d-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="faa2d-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="faa2d-119">Char</span><span class="sxs-lookup"><span data-stu-id="faa2d-119">Char</span></span>           | <span data-ttu-id="faa2d-120">Integer</span><span class="sxs-lookup"><span data-stu-id="faa2d-120">Integer</span></span>    | <span data-ttu-id="faa2d-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="faa2d-121">UTF-16</span></span>           |
| <span data-ttu-id="faa2d-122">Datetime</span><span class="sxs-lookup"><span data-stu-id="faa2d-122">DateTime</span></span>       | <span data-ttu-id="faa2d-123">Real</span><span class="sxs-lookup"><span data-stu-id="faa2d-123">Real</span></span>       | <span data-ttu-id="faa2d-124">Julianer Tageswert</span><span class="sxs-lookup"><span data-stu-id="faa2d-124">Julian day value</span></span> |
| <span data-ttu-id="faa2d-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="faa2d-125">DateTimeOffset</span></span> | <span data-ttu-id="faa2d-126">Real</span><span class="sxs-lookup"><span data-stu-id="faa2d-126">Real</span></span>       | <span data-ttu-id="faa2d-127">Julianer Tageswert</span><span class="sxs-lookup"><span data-stu-id="faa2d-127">Julian day value</span></span> |
| <span data-ttu-id="faa2d-128">Guid</span><span class="sxs-lookup"><span data-stu-id="faa2d-128">Guid</span></span>           | <span data-ttu-id="faa2d-129">Blob</span><span class="sxs-lookup"><span data-stu-id="faa2d-129">Blob</span></span>       |                  |
| <span data-ttu-id="faa2d-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="faa2d-130">TimeSpan</span></span>       | <span data-ttu-id="faa2d-131">Real</span><span class="sxs-lookup"><span data-stu-id="faa2d-131">Real</span></span>       | <span data-ttu-id="faa2d-132">In Tagen</span><span class="sxs-lookup"><span data-stu-id="faa2d-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="faa2d-133">Ausgabeparameter</span><span class="sxs-lookup"><span data-stu-id="faa2d-133">Output parameters</span></span>

<span data-ttu-id="faa2d-134">SQLite unterstützt keine Ausgabeparameter.</span><span class="sxs-lookup"><span data-stu-id="faa2d-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="faa2d-135">Geben Sie stattdessen Werte in den Abfrageergebnissen zurück.</span><span class="sxs-lookup"><span data-stu-id="faa2d-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="faa2d-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="faa2d-136">See also</span></span>

* [<span data-ttu-id="faa2d-137">Datentypen</span><span class="sxs-lookup"><span data-stu-id="faa2d-137">Data types</span></span>](types.md)
