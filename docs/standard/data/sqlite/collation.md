---
title: Sortierreihenfolge
ms.date: 12/13/2019
description: So erstellen Sie eine benutzerdefinierte Sortierungssequenz.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242971"
---
# <a name="collation"></a><span data-ttu-id="178f9-103">Sortierreihenfolge</span><span class="sxs-lookup"><span data-stu-id="178f9-103">Collation</span></span>

<span data-ttu-id="178f9-104">Sortierungssequenzen werden von SQLite beim Vergleichen von Textwerten verwendet, um die Reihenfolge und Gleichheit zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="178f9-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="178f9-105">Sie können angeben, welche Sortierung verwendet werden soll, wenn Spalten oder Vorgänge in SQL-Abfragen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="178f9-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="178f9-106">SQLite enthält standardmäßig drei Sortierungssequenzen.</span><span class="sxs-lookup"><span data-stu-id="178f9-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="178f9-107">Sortierreihenfolge</span><span class="sxs-lookup"><span data-stu-id="178f9-107">Collation</span></span> | <span data-ttu-id="178f9-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="178f9-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="178f9-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="178f9-109">RTRIM</span></span>     | <span data-ttu-id="178f9-110">Nachstehende Leerzeichen ignorieren</span><span class="sxs-lookup"><span data-stu-id="178f9-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="178f9-111">NOCASE</span><span class="sxs-lookup"><span data-stu-id="178f9-111">NOCASE</span></span>    | <span data-ttu-id="178f9-112">Groß-/Kleinschreibung für ASCII-Zeichen A bis Z wird nicht beachtet</span><span class="sxs-lookup"><span data-stu-id="178f9-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="178f9-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="178f9-113">BINARY</span></span>    | <span data-ttu-id="178f9-114">Groß-/Kleinschreibung wird beachtet,</span><span class="sxs-lookup"><span data-stu-id="178f9-114">Case-sensitive.</span></span> <span data-ttu-id="178f9-115">Bytes werden direkt verglichen</span><span class="sxs-lookup"><span data-stu-id="178f9-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="178f9-116">Benutzerdefinierte Sortierung</span><span class="sxs-lookup"><span data-stu-id="178f9-116">Custom collation</span></span>

<span data-ttu-id="178f9-117">Sie können auch eigene Sortierungssequenzen definieren oder die integrierten mit <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>überschreiben.</span><span class="sxs-lookup"><span data-stu-id="178f9-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="178f9-118">Das folgende Beispiel zeigt das Überschreiben der NOCASE-Sortierung zur Unterstützung von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="178f9-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="178f9-119">Der [vollständige Beispielcode](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) ist auf GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="178f9-119">The [full sample code](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="178f9-120">LIKE-Operator</span><span class="sxs-lookup"><span data-stu-id="178f9-120">Like operator</span></span>

<span data-ttu-id="178f9-121">Der LIKE-Operator in SQLite berücksichtigt keine Sortierungen.</span><span class="sxs-lookup"><span data-stu-id="178f9-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="178f9-122">Die Standardimplementierung weist dieselbe Semantik wie die NOCASE-Sortierung auf.</span><span class="sxs-lookup"><span data-stu-id="178f9-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="178f9-123">Nur für die ASCII-Zeichen A bis Z wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="178f9-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="178f9-124">Mithilfe der folgenden Pragmaanweisung wird bei Verwendung des LIKE-Operators die Groß-/Kleinschreibung berücksichtigt:</span><span class="sxs-lookup"><span data-stu-id="178f9-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="178f9-125">Ausführliche Informationen zum Überschreiben der Implementierung des LIKE-Operators finden Sie unter [Benutzerdefinierte Funktionen](user-defined-functions.md).</span><span class="sxs-lookup"><span data-stu-id="178f9-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="178f9-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="178f9-126">See also</span></span>

* [<span data-ttu-id="178f9-127">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="178f9-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="178f9-128">SQL-Syntax</span><span class="sxs-lookup"><span data-stu-id="178f9-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
