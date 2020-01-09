---
title: Interoperabilität
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie mit anderen SQLite-Bibliotheken zusammenarbeiten.
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450459"
---
# <a name="interoperability"></a>Interoperabilität

Microsoft. Data. sqlite verwendet sqlitepclraw für die Interaktion mit der systemeigenen SQLite-Bibliothek. Sqlitepclraw stellt eine schlanke .NET-API über die native SQLite-API bereit. Sqliteconnection und sqlitedatareader ermöglichen den Zugriff auf die zugrunde liegenden sqlitepclraw-Objekte, sodass Sie diese APIs direkt aufrufen können.

Im folgenden Beispiel wird gezeigt, wie `sqlite3_trace` aufgerufen wird, um ausgeführte SQL-Anweisungen in die Konsole zu schreiben:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

Das folgende Beispiel zeigt, wie Sie `sqlite3_stmt_status` aufrufen, um zu sehen, wie viele SQLite-VM-Schritte eine SQL-Anweisung in kompiliert hat:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

Die sqlitepclraw-Objekte machen sogar einen Zeiger auf die systemeigenen Objekte verfügbar, sodass Sie zusätzliche Native SQLite-APIs aufrufen/aufrufen können.
