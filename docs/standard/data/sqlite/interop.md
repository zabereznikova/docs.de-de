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
# <a name="interoperability"></a><span data-ttu-id="4f5b8-103">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="4f5b8-103">Interoperability</span></span>

<span data-ttu-id="4f5b8-104">Microsoft.Data.Sqlite verwendet SQLitePCLRaw für die Interaktion mit der nativen SQLite-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="4f5b8-104">Microsoft.Data.Sqlite uses SQLitePCLRaw to interact with the native SQLite library.</span></span> <span data-ttu-id="4f5b8-105">SQLitePCLRaw stellt eine schlanke .NET-API über die native SQLite-API bereit.</span><span class="sxs-lookup"><span data-stu-id="4f5b8-105">SQLitePCLRaw provides a thin .NET API over the native SQLite API.</span></span> <span data-ttu-id="4f5b8-106">SqliteConnection und SqliteDataReader ermöglichen den Zugriff auf die zugrunde liegenden SQLitePCLRaw-Objekte, sodass Sie diese APIs direkt aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="4f5b8-106">SqliteConnection and SqliteDataReader provide access to the underlying SQLitePCLRaw objects letting you call these APIs directly.</span></span>

<span data-ttu-id="4f5b8-107">Im folgenden Beispiel wird gezeigt, wie `sqlite3_trace` aufgerufen wird, um ausgeführte SQL-Anweisungen in die Konsole zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="4f5b8-107">The following example shows how to call `sqlite3_trace` to write executed SQL statements to the console:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

<span data-ttu-id="4f5b8-108">In diesem Beispiel wird wiederum gezeigt, wie Sie `sqlite3_stmt_status` aufrufen, um zu sehen, in wie viele SQL-VM-Schritte eine SQL-Anweisung kompiliert wurde:</span><span class="sxs-lookup"><span data-stu-id="4f5b8-108">And the following example shows calling `sqlite3_stmt_status` to see how many SQLite virtual machine steps a SQL statement compiled into:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

<span data-ttu-id="4f5b8-109">Die SQLitePCLRaw-Objekte machen sogar einen Zeiger auf die nativen Objekte verfügbar, sodass Sie zusätzliche native SQLite-APIs mit P/Invoke aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="4f5b8-109">The SQLitePCLRaw objects even expose a pointer to the native objects letting you P/Invoke additional native SQLite APIs.</span></span>
