---
title: Onlinesicherung
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie das Feature für die Online Sicherung von SQLite verwenden.
ms.openlocfilehash: 885aa2c5555b58deb2551c0a4e6933742a093457
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450345"
---
# <a name="online-backup"></a>Onlinesicherung

SQLite kann Datenbankdateien sichern, während die app ausgeführt wird. Diese Funktion ist in Microsoft. Data. sqlite als <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> Methode auf `SqliteConnection`verfügbar.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

Zurzeit werden `BackupDatabase` die Datenbank so schnell wie möglich sichern und andere Verbindungen daran hindert, in die Datenbank zu schreiben. Problem [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) wäre eine Alternative API zum Sichern der Datenbank im Hintergrund und ermöglicht anderen Verbindungen das Unterbrechen der Sicherung und das Schreiben in die Datenbank. Wenn Sie interessiert sind, geben Sie uns Feedback zu diesem Problem.
