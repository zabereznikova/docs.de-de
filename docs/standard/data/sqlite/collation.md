---
title: Sortierreihenfolge
ms.date: 12/13/2019
description: So erstellen Sie eine benutzerdefinierte Sortierungssequenz.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242971"
---
# <a name="collation"></a>Sortierreihenfolge

Sortierungssequenzen werden von SQLite beim Vergleichen von Textwerten verwendet, um die Reihenfolge und Gleichheit zu bestimmen. Sie können angeben, welche Sortierung verwendet werden soll, wenn Spalten oder Vorgänge in SQL-Abfragen erstellt werden. SQLite enthält standardmäßig drei Sortierungssequenzen.

| Sortierreihenfolge | Beschreibung                               |
| --------- | ----------------------------------------- |
| RTRIM     | Nachstehende Leerzeichen ignorieren               |
| NOCASE    | Groß-/Kleinschreibung für ASCII-Zeichen A bis Z wird nicht beachtet |
| BINARY    | Groß-/Kleinschreibung wird beachtet, Bytes werden direkt verglichen   |

## <a name="custom-collation"></a>Benutzerdefinierte Sortierung

Sie können auch eigene Sortierungssequenzen definieren oder die integrierten mit <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>überschreiben. Das folgende Beispiel zeigt das Überschreiben der NOCASE-Sortierung zur Unterstützung von Unicode-Zeichen. Der [vollständige Beispielcode](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) ist auf GitHub verfügbar.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>LIKE-Operator

Der LIKE-Operator in SQLite berücksichtigt keine Sortierungen. Die Standardimplementierung weist dieselbe Semantik wie die NOCASE-Sortierung auf. Nur für die ASCII-Zeichen A bis Z wird die Groß-/Kleinschreibung beachtet.

Mithilfe der folgenden Pragmaanweisung wird bei Verwendung des LIKE-Operators die Groß-/Kleinschreibung berücksichtigt:

```sql
PRAGMA case_sensitive_like = 1
```

Ausführliche Informationen zum Überschreiben der Implementierung des LIKE-Operators finden Sie unter [Benutzerdefinierte Funktionen](user-defined-functions.md).

## <a name="see-also"></a>Siehe auch

* [Benutzerdefinierte Funktionen](user-defined-functions.md)
* [SQL-Syntax](https://www.sqlite.org/lang.html)
