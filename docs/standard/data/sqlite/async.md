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
# <a name="async-limitations"></a>Async-Einschränkungen

SQLite unterstützt keine asynchronen E/A-Vorgänge. Asynchrone ADO.NET-Methoden werden synchron in Microsoft.Data.Sqlite ausgeführt. Sie sollten sie nicht aufrufen.

Verwenden Sie stattdessen einen [freigegebenen Cache](connection-strings.md#cache) und die [Write-Ahead-Protokollierung](https://www.sqlite.org/wal.html), um die Leistung und Parallelität zu verbessern.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> Die Write-Ahead-Protokollierung ist standardmäßig für Datenbanken aktiviert, die mithilfe von [Entity Framework Core](/ef/core/) erstellt wurden.
