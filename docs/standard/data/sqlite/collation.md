---
title: Collation
ms.date: 12/13/2019
description: Erfahren Sie, wie eine benutzerdefinierte Sortierreihenfolge erstellt wird.
ms.openlocfilehash: 0942ad4523a149ad74321cbe0f63021f53303579
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450285"
---
# <a name="collation"></a><span data-ttu-id="64298-103">Collation</span><span class="sxs-lookup"><span data-stu-id="64298-103">Collation</span></span>

<span data-ttu-id="64298-104">Sortierungs Sequenzen werden von SQLite beim Vergleichen von Text Werten verwendet, um die Reihenfolge und Gleichheit zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="64298-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="64298-105">Sie können angeben, welche Sortierung verwendet werden soll, wenn Spalten oder Vorgänge pro Vorgang in SQL-Abfragen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="64298-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="64298-106">SQLite enthält standardmäßig drei Sortier Sequenzen.</span><span class="sxs-lookup"><span data-stu-id="64298-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="64298-107">Collation</span><span class="sxs-lookup"><span data-stu-id="64298-107">Collation</span></span> | <span data-ttu-id="64298-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64298-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="64298-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="64298-109">RTRIM</span></span>     | <span data-ttu-id="64298-110">Nachfolgende Leerzeichen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="64298-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="64298-111">Keineschreibung</span><span class="sxs-lookup"><span data-stu-id="64298-111">NOCASE</span></span>    | <span data-ttu-id="64298-112">Groß-/Kleinschreibung für ASCII-Zeichen A-Z nicht beachtet</span><span class="sxs-lookup"><span data-stu-id="64298-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="64298-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="64298-113">BINARY</span></span>    | <span data-ttu-id="64298-114">Groß-/Kleinschreibung beachten.</span><span class="sxs-lookup"><span data-stu-id="64298-114">Case-sensitive.</span></span> <span data-ttu-id="64298-115">Vergleicht Bytes direkt</span><span class="sxs-lookup"><span data-stu-id="64298-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="64298-116">Benutzerdefinierte Sortierung</span><span class="sxs-lookup"><span data-stu-id="64298-116">Custom collation</span></span>

<span data-ttu-id="64298-117">Sie können auch eigene Sortierungs Sequenzen definieren oder die integrierten mit <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>überschreiben.</span><span class="sxs-lookup"><span data-stu-id="64298-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="64298-118">Das folgende Beispiel zeigt das Überschreiben der nocase-Sortierung zur Unterstützung von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="64298-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="64298-119">Den [vollständigen Beispielcode](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="64298-119">The [full sample code](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="64298-120">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="64298-120">Like operator</span></span>

<span data-ttu-id="64298-121">Der Like-Operator in SQLite berücksichtigt keine Sortierungen.</span><span class="sxs-lookup"><span data-stu-id="64298-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="64298-122">Die Standard Implementierung hat dieselbe Semantik wie die nocase-Sortierung.</span><span class="sxs-lookup"><span data-stu-id="64298-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="64298-123">Für die ASCII-Zeichen A bis Z wird nur die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="64298-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="64298-124">Mithilfe der folgenden Pragma-Anweisung können Sie den Like-Operator ganz einfach mit der Groß-/Kleinschreibung unterschieden:</span><span class="sxs-lookup"><span data-stu-id="64298-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 0
```

<span data-ttu-id="64298-125">Ausführliche Informationen zum Überschreiben der Implementierung des LIKE-Operators finden Sie unter [benutzerdefinierte Funktionen](user-defined-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="64298-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="64298-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64298-126">See also</span></span>

* [<span data-ttu-id="64298-127">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="64298-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="64298-128">SQL-Syntax</span><span class="sxs-lookup"><span data-stu-id="64298-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
