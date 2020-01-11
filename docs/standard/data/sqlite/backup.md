---
title: Onlinesicherung
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie das Feature für die Online Sicherung von SQLite verwenden.
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901286"
---
# <a name="online-backup"></a><span data-ttu-id="a4336-103">Onlinesicherung</span><span class="sxs-lookup"><span data-stu-id="a4336-103">Online backup</span></span>

<span data-ttu-id="a4336-104">SQLite kann Datenbankdateien sichern, während die app ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a4336-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="a4336-105">Diese Funktion ist in Microsoft. Data. sqlite als <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> Methode auf `SqliteConnection`verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4336-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="a4336-106">Zurzeit werden `BackupDatabase` die Datenbank so schnell wie möglich sichern und andere Verbindungen daran hindert, in die Datenbank zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a4336-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="a4336-107">Problem [#13834](https://github.com/dotnet/efcore/issues/13834) wäre eine Alternative API zum Sichern der Datenbank im Hintergrund und ermöglicht anderen Verbindungen das Unterbrechen der Sicherung und das Schreiben in die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a4336-107">Issue [#13834](https://github.com/dotnet/efcore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="a4336-108">Wenn Sie interessiert sind, geben Sie uns Feedback zu diesem Problem.</span><span class="sxs-lookup"><span data-stu-id="a4336-108">If you're interested, provide feedback on the issue.</span></span>
