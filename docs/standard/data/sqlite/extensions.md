---
title: Erweiterungen
ms.date: 12/13/2019
description: Erfahren Sie, wie SQLite-Erweiterungen geladen werden.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242958"
---
# <a name="extensions"></a>Erweiterungen

SQLite unterstützt das Laden von Erweiterungen zur Laufzeit. Erweiterungen umfassen beispielsweise zusätzliche SQL-Funktionen, Sortierungen und virtuelle Tabellen.

.NET Core enthält zusätzliche Logik für die Suche nach nativen Bibliotheken an zusätzlichen Orten wie NuGet-Paketen, auf die verwiesen wird. Leider kann SQLite diese Logik nicht nutzen, sondern ruft die Plattform-API direkt auf, um Bibliotheken zu laden. Daher müssen Sie möglicherweise vor dem Laden von SQLite-Erweiterungen den Pfad, LD_LIBRARY_PATH, oder DYLD_LIBRARY_PATH-Umgebungsvariablen ändern. In [einem Beispiel](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) auf GitHub wird gezeigt, wie Binärdateien für die aktuelle Runtime in einem NuGet-Paket gefunden werden können, auf das verwiesen wird.

Rufen Sie die Methode <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> auf, um Erweiterungen zu laden. Microsoft.Data.Sqlite stellt sicher, dass die Erweiterung geladen bleibt, auch wenn die Verbindung geschlossen und erneut geöffnet wird.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>Siehe auch

* [Zur Laufzeit ladbare Erweiterungen](https://www.sqlite.org/loadext.html)
