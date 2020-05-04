---
title: Onlinesicherung
ms.date: 12/13/2019
description: In diesem Artikel erfahren Sie, wie Sie das Onlinesicherungsfeature von SQLite verwenden.
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901286"
---
# <a name="online-backup"></a><span data-ttu-id="c9f3a-103">Onlinesicherung</span><span class="sxs-lookup"><span data-stu-id="c9f3a-103">Online backup</span></span>

<span data-ttu-id="c9f3a-104">SQLite kann Datenbankdateien sichern, während die App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c9f3a-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="c9f3a-105">Diese Funktion ist in Microsoft.Data.Sqlite als <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A>-Methode für `SqliteConnection` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c9f3a-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="c9f3a-106">Aktuell sichert `BackupDatabase` die Datenbank schnellstmöglich und blockiert, dass andere Verbindungen Schreibvorgänge in der Datenbank ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9f3a-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="c9f3a-107">Das Issue [#13834](https://github.com/dotnet/efcore/issues/13834) würde eine alternative API bereitstellen, um die Datenbank im Hintergrund zu sichern und es ermöglichen, dass andere Verbindungen die Sicherung unterbrechen, um Schreibvorgänge in der Datenbank auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c9f3a-107">Issue [#13834](https://github.com/dotnet/efcore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="c9f3a-108">Wenn Sie an dieser Funktion interessiert sind, können Sie Feedback zum Issue geben.</span><span class="sxs-lookup"><span data-stu-id="c9f3a-108">If you're interested, provide feedback on the issue.</span></span>
