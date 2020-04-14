---
title: Erweiterungen
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie SQLite-Erweiterungen laden.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242958"
---
# <a name="extensions"></a>Erweiterungen

SQLite unterstützt das Laden von Erweiterungen zur Laufzeit. Erweiterungen umfassen Dinge wie zusätzliche SQL-Funktionen, Sortierungen, virtuelle Tabellen und mehr.

.NET Core enthält zusätzliche Logik zum Auffinden systemeigener Bibliotheken an zusätzlichen Orten wie nuGet-Paketen. Leider kann SQLite diese Logik nicht nutzen; Die Plattform-API wird direkt zum Laden von Bibliotheken auf. Aus diesem Grund müssen Sie möglicherweise die Umgebungsvariablen PATH, LD_LIBRARY_PATH oder DYLD_LIBRARY_PATH ändern, bevor Sie SQLite-Erweiterungen laden. Es gibt [ein Beispiel](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) auf GitHub, das das Suchen von Binärdateien für die aktuelle Laufzeit in einem referenzierten NuGet-Paket veranschaulicht.

Um eine Erweiterung zu <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> laden, rufen Sie die Methode auf. Microsoft.Data.Sqlite stellt sicher, dass die Erweiterung auch dann geladen bleibt, wenn die Verbindung geschlossen und erneut geöffnet wird.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>Siehe auch

* [Laufzeit-Ladeerweiterungen](https://www.sqlite.org/loadext.html)
