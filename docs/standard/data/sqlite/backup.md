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
# <a name="online-backup"></a>Onlinesicherung

SQLite kann Datenbankdateien sichern, während die App ausgeführt wird. Diese Funktion ist in Microsoft.Data.Sqlite als <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A>-Methode für `SqliteConnection` verfügbar.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

Aktuell sichert `BackupDatabase` die Datenbank schnellstmöglich und blockiert, dass andere Verbindungen Schreibvorgänge in der Datenbank ausführen. Das Issue [#13834](https://github.com/dotnet/efcore/issues/13834) würde eine alternative API bereitstellen, um die Datenbank im Hintergrund zu sichern und es ermöglichen, dass andere Verbindungen die Sicherung unterbrechen, um Schreibvorgänge in der Datenbank auszuführen. Wenn Sie an dieser Funktion interessiert sind, können Sie Feedback zum Issue geben.
