---
title: In-Memory-Datenbanken
ms.date: 12/13/2019
description: In diesem Artikel erfahren Sie, wie Sie SQLite-In-Memory-Datenbanken verwenden.
ms.openlocfilehash: fbda5787d95a9ce462752b985f847af0b0551fa6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555366"
---
# <a name="in-memory-databases"></a><span data-ttu-id="7f5f1-103">In-Memory-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="7f5f1-103">In-memory databases</span></span>

<span data-ttu-id="7f5f1-104">SQLite-In-Memory-Datenbanken sind Datenbanken, die vollständig auf dem Arbeitsspeicher gespeichert sind, nicht auf einem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="7f5f1-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="7f5f1-105">Verwenden Sie den speziellen Datenquellendateiname `:memory:`, um eine In-Memory-Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f5f1-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="7f5f1-106">Wenn die Verbindung beendet wird, wird die Datenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7f5f1-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="7f5f1-107">Wenn `:memory:` verwendet wird, erstellt jede Verbindung ihre eigene Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7f5f1-107">When using `:memory:`, each connection creates its own database.</span></span>

```connectionstring
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="7f5f1-108">Freigabefähige In-Memory-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="7f5f1-108">Shareable in-memory databases</span></span>

<span data-ttu-id="7f5f1-109">In-Memory-Datenbanken können für mehrere Verbindungen freigegeben werden, indem in der Verbindungszeichenfolge `Mode=Memory` und `Cache=Shared` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f5f1-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="7f5f1-110">Das `Data Source`-Schlüsselwort wird verwendet, um die In-Memory-Datenbank zu benennen.</span><span class="sxs-lookup"><span data-stu-id="7f5f1-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="7f5f1-111">Verbindungszeichenfolgen, für die derselbe Name verwendet wird, greifen auf dieselbe In-Memory-Datenbank zu.</span><span class="sxs-lookup"><span data-stu-id="7f5f1-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="7f5f1-112">Die Datenbank besteht, solange mindestens eine Verbindung zu ihr offen bleibt.</span><span class="sxs-lookup"><span data-stu-id="7f5f1-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="7f5f1-113">Ein [Beispiel](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) hierfür finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="7f5f1-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```connectionstring
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
