---
title: -Erweiterungen
ms.date: 12/13/2019
description: Erfahren Sie, wie SQLite-Erweiterungen geladen werden.
ms.openlocfilehash: 74b207205492bac48c89cb756470326f8e4a13c4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777373"
---
# <a name="extensions"></a>-Erweiterungen

SQLite unterstützt das Laden von Erweiterungen zur Laufzeit. Erweiterungen umfassen beispielsweise zusätzliche SQL-Funktionen, Sortierungen, virtuelle Tabellen und vieles mehr.

.Net Core enthält zusätzliche Logik für die Suche nach nativen Bibliotheken an zusätzlichen Stellen wie referenzierte nuget-Pakete. Leider kann SQLite diese Logik nicht nutzen. Sie ruft die Platform-API direkt zum Laden von Bibliotheken auf. Daher muss Ihre APP möglicherweise die Pfad-, LD_LIBRARY_PATH-oder DYLD_LIBRARY_PATH Umgebungsvariablen ändern, bevor SQLite-Erweiterungen geladen werden. Auf GitHub finden Sie [ein Beispiel](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) , das die Suche nach Binärdateien für die aktuelle Laufzeit innerhalb eines referenzierten nuget-Pakets veranschaulicht.

Zum Laden einer Erweiterung wird die <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>-Methode aufgerufen. Microsoft. Data. sqlite stellt sicher, dass die Erweiterung weiterhin geladen wird, auch wenn die Verbindung geschlossen und erneut geöffnet wird.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>Siehe auch

* [Ausführbare Lauf Zeit Erweiterungen](https://www.sqlite.org/loadext.html)
