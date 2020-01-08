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
# <a name="interoperability"></a><span data-ttu-id="1aeb9-103">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="1aeb9-103">Interoperability</span></span>

<span data-ttu-id="1aeb9-104">Microsoft. Data. sqlite verwendet sqlitepclraw für die Interaktion mit der systemeigenen SQLite-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="1aeb9-104">Microsoft.Data.Sqlite uses SQLitePCLRaw to interact with the native SQLite library.</span></span> <span data-ttu-id="1aeb9-105">Sqlitepclraw stellt eine schlanke .NET-API über die native SQLite-API bereit.</span><span class="sxs-lookup"><span data-stu-id="1aeb9-105">SQLitePCLRaw provides a thin .NET API over the native SQLite API.</span></span> <span data-ttu-id="1aeb9-106">Sqliteconnection und sqlitedatareader ermöglichen den Zugriff auf die zugrunde liegenden sqlitepclraw-Objekte, sodass Sie diese APIs direkt aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="1aeb9-106">SqliteConnection and SqliteDataReader provide access to the underlying SQLitePCLRaw objects letting you call these APIs directly.</span></span>

<span data-ttu-id="1aeb9-107">Im folgenden Beispiel wird gezeigt, wie `sqlite3_trace` aufgerufen wird, um ausgeführte SQL-Anweisungen in die Konsole zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="1aeb9-107">The following example shows how to call `sqlite3_trace` to write executed SQL statements to the console:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

<span data-ttu-id="1aeb9-108">Das folgende Beispiel zeigt, wie Sie `sqlite3_stmt_status` aufrufen, um zu sehen, wie viele SQLite-VM-Schritte eine SQL-Anweisung in kompiliert hat:</span><span class="sxs-lookup"><span data-stu-id="1aeb9-108">And the following example shows calling `sqlite3_stmt_status` to see how many SQLite virtual machine steps a SQL statement compiled into:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

<span data-ttu-id="1aeb9-109">Die sqlitepclraw-Objekte machen sogar einen Zeiger auf die systemeigenen Objekte verfügbar, sodass Sie zusätzliche Native SQLite-APIs aufrufen/aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="1aeb9-109">The SQLitePCLRaw objects even expose a pointer to the native objects letting you P/Invoke additional native SQLite APIs.</span></span>
