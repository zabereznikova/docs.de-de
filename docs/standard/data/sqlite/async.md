---
title: Async-Einschränkungen
ms.date: 12/13/2019
description: Erläutert die Einschränkungen der Async-APIs und einige Alternativen, die Sie stattdessen verwenden können.
ms.openlocfilehash: 350237dc5c03023f60e9680e8b9c94aabb62606f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450333"
---
# <a name="async-limitations"></a><span data-ttu-id="b9fd1-103">Async-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b9fd1-103">Async limitations</span></span>

<span data-ttu-id="b9fd1-104">SQLite unterstützt keine asynchronen e/a-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="b9fd1-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="b9fd1-105">Async-ADO.NET-Methoden werden synchron in Microsoft. Data. sqlite ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b9fd1-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="b9fd1-106">Vermeiden Sie den Aufruf.</span><span class="sxs-lookup"><span data-stu-id="b9fd1-106">Avoid calling them.</span></span>

<span data-ttu-id="b9fd1-107">Verwenden Sie stattdessen die [Write-Ahead-Protokollierung](https://www.sqlite.org/wal.html) , um Leistung und Parallelität zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b9fd1-107">Instead, use [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="b9fd1-108">Die Write-Ahead-Protokollierung ist für mit [Entity Framework Core](/ef/core/)erstellte Datenbanken standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b9fd1-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
