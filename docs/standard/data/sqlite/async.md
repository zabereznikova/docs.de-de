---
title: Async-Einschränkungen
ms.date: 12/13/2019
description: Erläutert die Einschränkungen von asynchronen APIs und einige Alternativen, die Sie stattdessen verwenden können
ms.openlocfilehash: 350237dc5c03023f60e9680e8b9c94aabb62606f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450333"
---
# <a name="async-limitations"></a>Async-Einschränkungen

SQLite unterstützt keine asynchronen E/A-Vorgänge. Asynchrone ADO.NET-Methoden werden synchron in Microsoft.Data.Sqlite ausgeführt. Sie sollten sie nicht aufrufen.

Verwenden Sie stattdessen die [Write-Ahead-Protokollierung](https://www.sqlite.org/wal.html), um die Leistung und die Parallelität zu verbessern.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> Die Write-Ahead-Protokollierung ist standardmäßig für Datenbanken aktiviert, die mithilfe von [Entity Framework Core](/ef/core/) erstellt wurden.
