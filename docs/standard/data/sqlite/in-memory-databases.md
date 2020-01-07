---
title: In-Memory-Datenbanken
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie in-Memory-SQLite-Datenbanken verwenden.
ms.openlocfilehash: b125ff5aa4128bd4c3ff558c5573b7d11802090a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450465"
---
# <a name="in-memory-databases"></a><span data-ttu-id="7f298-103">In-Memory-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="7f298-103">In-memory databases</span></span>

<span data-ttu-id="7f298-104">SQLite-in-Memory-Datenbanken sind Datenbanken, die vollständig im Arbeitsspeicher gespeichert sind, nicht auf</span><span class="sxs-lookup"><span data-stu-id="7f298-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="7f298-105">Verwenden Sie den Dateinamen der speziellen Datenquelle `:memory:`, um eine in-Memory Database zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f298-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="7f298-106">Wenn die Verbindung geschlossen wird, wird die Datenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7f298-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="7f298-107">Wenn Sie `:memory:`verwenden, erstellt jede Verbindung eine eigene Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7f298-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="7f298-108">Share Bare in-Memory-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="7f298-108">Shareable in-memory databases</span></span>

<span data-ttu-id="7f298-109">In-Memory-Datenbanken können mithilfe von `Mode=Memory` und `Cache=Shared` in der Verbindungs Zeichenfolge von mehreren Verbindungen gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="7f298-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="7f298-110">Das `Data Source`-Schlüsselwort wird verwendet, um dem in-Memory Database einen Namen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="7f298-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="7f298-111">Verbindungs Zeichenfolgen, die denselben Namen verwenden, greifen auf denselben in-Memory Database zu.</span><span class="sxs-lookup"><span data-stu-id="7f298-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="7f298-112">Die Datenbank bleibt bestehen, solange mindestens eine Verbindung mit ihr geöffnet bleibt.</span><span class="sxs-lookup"><span data-stu-id="7f298-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="7f298-113">Ein [Beispiel](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) , das zeigt, ist auf GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7f298-113">A [sample](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
