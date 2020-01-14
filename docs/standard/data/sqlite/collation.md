---
title: Collation
ms.date: 12/13/2019
description: Erfahren Sie, wie eine benutzerdefinierte Sortierreihenfolge erstellt wird.
ms.openlocfilehash: 9cc574a75c8f5347dd9bb44e36af72e50afa57b4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777390"
---
# <a name="collation"></a>Collation

Sortierungs Sequenzen werden von SQLite beim Vergleichen von Text Werten verwendet, um die Reihenfolge und Gleichheit zu bestimmen. Sie können angeben, welche Sortierung verwendet werden soll, wenn Spalten oder Vorgänge pro Vorgang in SQL-Abfragen erstellt werden. SQLite enthält standardmäßig drei Sortier Sequenzen.

| Collation | Beschreibung                               |
| --------- | ----------------------------------------- |
| RTRIM     | Nachfolgende Leerzeichen werden ignoriert.               |
| Keineschreibung    | Groß-/Kleinschreibung für ASCII-Zeichen A-Z nicht beachtet |
| BINARY    | Groß-/Kleinschreibung beachten. Vergleicht Bytes direkt   |

## <a name="custom-collation"></a>Benutzerdefinierte Sortierung

Sie können auch eigene Sortierungs Sequenzen definieren oder die integrierten mit <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>überschreiben. Das folgende Beispiel zeigt das Überschreiben der nocase-Sortierung zur Unterstützung von Unicode-Zeichen. Den [vollständigen Beispielcode](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) finden Sie auf GitHub.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like-Operator

Der Like-Operator in SQLite berücksichtigt keine Sortierungen. Die Standard Implementierung hat dieselbe Semantik wie die nocase-Sortierung. Für die ASCII-Zeichen A bis Z wird nur die Groß-/Kleinschreibung beachtet.

Mithilfe der folgenden Pragma-Anweisung können Sie den Like-Operator ganz einfach mit der Groß-/Kleinschreibung unterschieden:

```sql
PRAGMA case_sensitive_like = 0
```

Ausführliche Informationen zum Überschreiben der Implementierung des LIKE-Operators finden Sie unter [benutzerdefinierte Funktionen](user-defined-functions.md) .

## <a name="see-also"></a>Siehe auch

* [Benutzerdefinierte Funktionen](user-defined-functions.md)
* [SQL-Syntax](https://www.sqlite.org/lang.html)
