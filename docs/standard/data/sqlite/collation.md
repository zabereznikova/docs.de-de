---
title: Sortierung
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie eine benutzerdefinierte Sortiersequenz erstellen.
ms.openlocfilehash: b93c82a4ace154b8293b05effa8f9e9294fa7708
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79506540"
---
# <a name="collation"></a><span data-ttu-id="08858-103">Sortierung</span><span class="sxs-lookup"><span data-stu-id="08858-103">Collation</span></span>

<span data-ttu-id="08858-104">Beim Vergleichen von TEXT-Werten zur Bestimmung von Reihenfolge und Gleichheit werden von SQLite SQLite SQLite SQLite summieren.</span><span class="sxs-lookup"><span data-stu-id="08858-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="08858-105">Sie können angeben, welche Sortierung beim Erstellen von Spalten oder pro Vorgang in SQL-Abfragen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08858-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="08858-106">SQLite enthält standardmäßig drei Sortiersequenzen.</span><span class="sxs-lookup"><span data-stu-id="08858-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="08858-107">Sortierung</span><span class="sxs-lookup"><span data-stu-id="08858-107">Collation</span></span> | <span data-ttu-id="08858-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08858-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="08858-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="08858-109">RTRIM</span></span>     | <span data-ttu-id="08858-110">Ignoriert nachgestellte Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="08858-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="08858-111">NOCASE</span><span class="sxs-lookup"><span data-stu-id="08858-111">NOCASE</span></span>    | <span data-ttu-id="08858-112">Groß-/Kleinschreibung für ASCII-Zeichen A-Z</span><span class="sxs-lookup"><span data-stu-id="08858-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="08858-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="08858-113">BINARY</span></span>    | <span data-ttu-id="08858-114">Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="08858-114">Case-sensitive.</span></span> <span data-ttu-id="08858-115">Vergleicht Bytes direkt</span><span class="sxs-lookup"><span data-stu-id="08858-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="08858-116">Benutzerdefinierte Sortierung</span><span class="sxs-lookup"><span data-stu-id="08858-116">Custom collation</span></span>

<span data-ttu-id="08858-117">Sie können auch eigene Sortiersequenzen definieren oder die integrierten <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>mithilfe von überschreiben.</span><span class="sxs-lookup"><span data-stu-id="08858-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="08858-118">Das folgende Beispiel zeigt das Überschreiben der NOCASE-Kollatierung zur Unterstützung von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="08858-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="08858-119">Der [vollständige Beispielcode](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) ist auf GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="08858-119">The [full sample code](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="08858-120">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="08858-120">Like operator</span></span>

<span data-ttu-id="08858-121">Der LIKE-Operator in SQLite berücksichtigt keine Sortierungen.</span><span class="sxs-lookup"><span data-stu-id="08858-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="08858-122">Die Standardimplementierung hat die gleiche Semantik wie die NOCASE-Kollatierung.</span><span class="sxs-lookup"><span data-stu-id="08858-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="08858-123">Für die ASCII-Zeichen A bis Z wird nur die Groß-/Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="08858-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="08858-124">Sie können die Groß-/Kleinschreibung des LIKE-Operators mithilfe der folgenden pragma-Anweisung einfach berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="08858-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="08858-125">Weitere Informationen zum Überschreiben der Implementierung des LIKE-Operators finden Sie unter [Benutzerdefinierte Funktionen.](user-defined-functions.md)</span><span class="sxs-lookup"><span data-stu-id="08858-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="08858-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08858-126">See also</span></span>

* [<span data-ttu-id="08858-127">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="08858-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="08858-128">SQL-Syntax</span><span class="sxs-lookup"><span data-stu-id="08858-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
