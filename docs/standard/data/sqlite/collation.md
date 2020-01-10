---
title: Collation
ms.date: 12/13/2019
description: Erfahren Sie, wie eine benutzerdefinierte Sortierreihenfolge erstellt wird.
ms.openlocfilehash: 9cc574a75c8f5347dd9bb44e36af72e50afa57b4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777390"
---
# <a name="collation"></a><span data-ttu-id="4c5d3-103">Collation</span><span class="sxs-lookup"><span data-stu-id="4c5d3-103">Collation</span></span>

<span data-ttu-id="4c5d3-104">Sortierungs Sequenzen werden von SQLite beim Vergleichen von Text Werten verwendet, um die Reihenfolge und Gleichheit zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="4c5d3-105">Sie können angeben, welche Sortierung verwendet werden soll, wenn Spalten oder Vorgänge pro Vorgang in SQL-Abfragen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="4c5d3-106">SQLite enthält standardmäßig drei Sortier Sequenzen.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="4c5d3-107">Collation</span><span class="sxs-lookup"><span data-stu-id="4c5d3-107">Collation</span></span> | <span data-ttu-id="4c5d3-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c5d3-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="4c5d3-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="4c5d3-109">RTRIM</span></span>     | <span data-ttu-id="4c5d3-110">Nachfolgende Leerzeichen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="4c5d3-111">Keineschreibung</span><span class="sxs-lookup"><span data-stu-id="4c5d3-111">NOCASE</span></span>    | <span data-ttu-id="4c5d3-112">Groß-/Kleinschreibung für ASCII-Zeichen A-Z nicht beachtet</span><span class="sxs-lookup"><span data-stu-id="4c5d3-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="4c5d3-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="4c5d3-113">BINARY</span></span>    | <span data-ttu-id="4c5d3-114">Groß-/Kleinschreibung beachten.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-114">Case-sensitive.</span></span> <span data-ttu-id="4c5d3-115">Vergleicht Bytes direkt</span><span class="sxs-lookup"><span data-stu-id="4c5d3-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="4c5d3-116">Benutzerdefinierte Sortierung</span><span class="sxs-lookup"><span data-stu-id="4c5d3-116">Custom collation</span></span>

<span data-ttu-id="4c5d3-117">Sie können auch eigene Sortierungs Sequenzen definieren oder die integrierten mit <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>überschreiben.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="4c5d3-118">Das folgende Beispiel zeigt das Überschreiben der nocase-Sortierung zur Unterstützung von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="4c5d3-119">Den [vollständigen Beispielcode](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-119">The [full sample code](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="4c5d3-120">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="4c5d3-120">Like operator</span></span>

<span data-ttu-id="4c5d3-121">Der Like-Operator in SQLite berücksichtigt keine Sortierungen.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="4c5d3-122">Die Standard Implementierung hat dieselbe Semantik wie die nocase-Sortierung.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="4c5d3-123">Für die ASCII-Zeichen A bis Z wird nur die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="4c5d3-124">Mithilfe der folgenden Pragma-Anweisung können Sie den Like-Operator ganz einfach mit der Groß-/Kleinschreibung unterschieden:</span><span class="sxs-lookup"><span data-stu-id="4c5d3-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 0
```

<span data-ttu-id="4c5d3-125">Ausführliche Informationen zum Überschreiben der Implementierung des LIKE-Operators finden Sie unter [benutzerdefinierte Funktionen](user-defined-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="4c5d3-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c5d3-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c5d3-126">See also</span></span>

* [<span data-ttu-id="4c5d3-127">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="4c5d3-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="4c5d3-128">SQL-Syntax</span><span class="sxs-lookup"><span data-stu-id="4c5d3-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
