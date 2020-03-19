---
title: Sortierung
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie eine benutzerdefinierte Sortiersequenz erstellen.
ms.openlocfilehash: b93c82a4ace154b8293b05effa8f9e9294fa7708
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79506540"
---
# <a name="collation"></a>Sortierung

Beim Vergleichen von TEXT-Werten zur Bestimmung von Reihenfolge und Gleichheit werden von SQLite SQLite SQLite SQLite summieren. Sie können angeben, welche Sortierung beim Erstellen von Spalten oder pro Vorgang in SQL-Abfragen verwendet werden soll. SQLite enthält standardmäßig drei Sortiersequenzen.

| Sortierung | Beschreibung                               |
| --------- | ----------------------------------------- |
| RTRIM     | Ignoriert nachgestellte Leerzeichen               |
| NOCASE    | Groß-/Kleinschreibung für ASCII-Zeichen A-Z |
| BINARY    | Groß-/Kleinschreibung. Vergleicht Bytes direkt   |

## <a name="custom-collation"></a>Benutzerdefinierte Sortierung

Sie können auch eigene Sortiersequenzen definieren oder die integrierten <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>mithilfe von überschreiben. Das folgende Beispiel zeigt das Überschreiben der NOCASE-Kollatierung zur Unterstützung von Unicode-Zeichen. Der [vollständige Beispielcode](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) ist auf GitHub verfügbar.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like-Operator

Der LIKE-Operator in SQLite berücksichtigt keine Sortierungen. Die Standardimplementierung hat die gleiche Semantik wie die NOCASE-Kollatierung. Für die ASCII-Zeichen A bis Z wird nur die Groß-/Kleinschreibung nicht berücksichtigt.

Sie können die Groß-/Kleinschreibung des LIKE-Operators mithilfe der folgenden pragma-Anweisung einfach berücksichtigen:

```sql
PRAGMA case_sensitive_like = 1
```

Weitere Informationen zum Überschreiben der Implementierung des LIKE-Operators finden Sie unter [Benutzerdefinierte Funktionen.](user-defined-functions.md)

## <a name="see-also"></a>Weitere Informationen

* [Benutzerdefinierte Funktionen](user-defined-functions.md)
* [SQL-Syntax](https://www.sqlite.org/lang.html)
