---
title: Async-Einschränkungen
ms.date: 09/04/2020
description: Erläutert die Einschränkungen von asynchronen APIs und einige Alternativen, die Sie stattdessen verwenden können
ms.openlocfilehash: 8b14fcfeb12d331d8d43ca6d77332007a12ae5dc
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515994"
---
# <a name="async-limitations"></a><span data-ttu-id="eff23-103">Async-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="eff23-103">Async limitations</span></span>

<span data-ttu-id="eff23-104">SQLite unterstützt keine asynchronen E/A-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="eff23-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="eff23-105">Asynchrone ADO.NET-Methoden werden synchron in Microsoft.Data.Sqlite ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="eff23-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="eff23-106">Sie sollten sie nicht aufrufen.</span><span class="sxs-lookup"><span data-stu-id="eff23-106">Avoid calling them.</span></span>

<span data-ttu-id="eff23-107">Verwenden Sie stattdessen einen [freigegebenen Cache](connection-strings.md#cache) und die [Write-Ahead-Protokollierung](https://www.sqlite.org/wal.html), um die Leistung und Parallelität zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="eff23-107">Instead, use a [shared cache](connection-strings.md#cache) and [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="eff23-108">Die Write-Ahead-Protokollierung ist standardmäßig für Datenbanken aktiviert, die mithilfe von [Entity Framework Core](/ef/core/) erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="eff23-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
