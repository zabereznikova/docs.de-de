---
title: Interoperabilität
ms.date: 12/13/2019
description: Informationen zur Interoperabilität mit anderen SQLite-Bibliotheken
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450459"
---
# <a name="interoperability"></a>Interoperabilität

Microsoft.Data.Sqlite verwendet SQLitePCLRaw für die Interaktion mit der nativen SQLite-Bibliothek. SQLitePCLRaw stellt eine schlanke .NET-API über die native SQLite-API bereit. SqliteConnection und SqliteDataReader ermöglichen den Zugriff auf die zugrunde liegenden SQLitePCLRaw-Objekte, sodass Sie diese APIs direkt aufrufen können.

Im folgenden Beispiel wird gezeigt, wie `sqlite3_trace` aufgerufen wird, um ausgeführte SQL-Anweisungen in die Konsole zu schreiben:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

In diesem Beispiel wird wiederum gezeigt, wie Sie `sqlite3_stmt_status` aufrufen, um zu sehen, in wie viele SQL-VM-Schritte eine SQL-Anweisung kompiliert wurde:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

Die SQLitePCLRaw-Objekte machen sogar einen Zeiger auf die nativen Objekte verfügbar, sodass Sie zusätzliche native SQLite-APIs mit P/Invoke aufrufen können.
