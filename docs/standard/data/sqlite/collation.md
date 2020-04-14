---
title: Sortierung
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie eine benutzerdefinierte Sortiersequenz erstellen.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242971"
---
# <a name="collation"></a>Sortierung

Beim Vergleichen von TEXT-Werten zur Bestimmung von Reihenfolge und Gleichheit werden von SQLite SQLite SQLite SQLite summieren. Sie können angeben, welche Sortierung beim Erstellen von Spalten oder pro Vorgang in SQL-Abfragen verwendet werden soll. SQLite enthält standardmäßig drei Sortiersequenzen.

| Sortierung | BESCHREIBUNG                               |
| --------- | ----------------------------------------- |
| RTRIM     | Ignoriert nachgestellte Leerzeichen               |
| NOCASE    | Groß-/Kleinschreibung für ASCII-Zeichen A-Z |
| BINARY    | Groß-/Kleinschreibung. Vergleicht Bytes direkt   |

## <a name="custom-collation"></a>Benutzerdefinierte Sortierung

Sie können auch eigene Sortiersequenzen definieren oder die integrierten <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>mithilfe von überschreiben. Das folgende Beispiel zeigt das Überschreiben der NOCASE-Kollatierung zur Unterstützung von Unicode-Zeichen. Der [vollständige Beispielcode](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) ist auf GitHub verfügbar.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like-Operator

Der LIKE-Operator in SQLite berücksichtigt keine Sortierungen. Die Standardimplementierung hat die gleiche Semantik wie die NOCASE-Kollatierung. Für die ASCII-Zeichen A bis Z wird nur die Groß-/Kleinschreibung nicht berücksichtigt.

Sie können die Groß-/Kleinschreibung des LIKE-Operators mithilfe der folgenden pragma-Anweisung einfach berücksichtigen:

```sql
PRAGMA case_sensitive_like = 1
```

Weitere Informationen zum Überschreiben der Implementierung des LIKE-Operators finden Sie unter [Benutzerdefinierte Funktionen.](user-defined-functions.md)

## <a name="see-also"></a>Siehe auch

* [Benutzerdefinierte Funktionen](user-defined-functions.md)
* [SQL-Syntax](https://www.sqlite.org/lang.html)
