---
title: Sortierung
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie eine benutzerdefinierte Sortiersequenz erstellen.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242971"
---
# <a name="collation"></a><span data-ttu-id="f2fc8-103">Sortierung</span><span class="sxs-lookup"><span data-stu-id="f2fc8-103">Collation</span></span>

<span data-ttu-id="f2fc8-104">Beim Vergleichen von TEXT-Werten zur Bestimmung von Reihenfolge und Gleichheit werden von SQLite SQLite SQLite SQLite summieren.</span><span class="sxs-lookup"><span data-stu-id="f2fc8-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="f2fc8-105">Sie können angeben, welche Sortierung beim Erstellen von Spalten oder pro Vorgang in SQL-Abfragen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f2fc8-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="f2fc8-106">SQLite enthält standardmäßig drei Sortiersequenzen.</span><span class="sxs-lookup"><span data-stu-id="f2fc8-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="f2fc8-107">Sortierung</span><span class="sxs-lookup"><span data-stu-id="f2fc8-107">Collation</span></span> | <span data-ttu-id="f2fc8-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f2fc8-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="f2fc8-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="f2fc8-109">RTRIM</span></span>     | <span data-ttu-id="f2fc8-110">Ignoriert nachgestellte Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="f2fc8-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="f2fc8-111">NOCASE</span><span class="sxs-lookup"><span data-stu-id="f2fc8-111">NOCASE</span></span>    | <span data-ttu-id="f2fc8-112">Groß-/Kleinschreibung für ASCII-Zeichen A-Z</span><span class="sxs-lookup"><span data-stu-id="f2fc8-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="f2fc8-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="f2fc8-113">BINARY</span></span>    | <span data-ttu-id="f2fc8-114">Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="f2fc8-114">Case-sensitive.</span></span> <span data-ttu-id="f2fc8-115">Vergleicht Bytes direkt</span><span class="sxs-lookup"><span data-stu-id="f2fc8-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="f2fc8-116">Benutzerdefinierte Sortierung</span><span class="sxs-lookup"><span data-stu-id="f2fc8-116">Custom collation</span></span>

<span data-ttu-id="f2fc8-117">Sie können auch eigene Sortiersequenzen definieren oder die integrierten <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>mithilfe von überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f2fc8-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="f2fc8-118">Das folgende Beispiel zeigt das Überschreiben der NOCASE-Kollatierung zur Unterstützung von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f2fc8-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="f2fc8-119">Der [vollständige Beispielcode](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) ist auf GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f2fc8-119">The [full sample code](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="f2fc8-120">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="f2fc8-120">Like operator</span></span>

<span data-ttu-id="f2fc8-121">Der LIKE-Operator in SQLite berücksichtigt keine Sortierungen.</span><span class="sxs-lookup"><span data-stu-id="f2fc8-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="f2fc8-122">Die Standardimplementierung hat die gleiche Semantik wie die NOCASE-Kollatierung.</span><span class="sxs-lookup"><span data-stu-id="f2fc8-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="f2fc8-123">Für die ASCII-Zeichen A bis Z wird nur die Groß-/Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="f2fc8-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="f2fc8-124">Sie können die Groß-/Kleinschreibung des LIKE-Operators mithilfe der folgenden pragma-Anweisung einfach berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="f2fc8-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="f2fc8-125">Weitere Informationen zum Überschreiben der Implementierung des LIKE-Operators finden Sie unter [Benutzerdefinierte Funktionen.](user-defined-functions.md)</span><span class="sxs-lookup"><span data-stu-id="f2fc8-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2fc8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2fc8-126">See also</span></span>

* [<span data-ttu-id="f2fc8-127">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="f2fc8-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="f2fc8-128">SQL-Syntax</span><span class="sxs-lookup"><span data-stu-id="f2fc8-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
