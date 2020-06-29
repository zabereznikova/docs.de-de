---
title: Parameter
ms.date: 12/13/2019
description: Hier erfahren Sie mehr über die Verwendung von SQL-Parametern.
ms.openlocfilehash: b24610a5cb65e2b24171452acef9bf55b4995431
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768949"
---
# <a name="parameters"></a>Parameter

Parameter werden zum Schutz vor Angriffen durch Einschleusung von SQL-Befehlen verwendet. Anstatt Benutzereingaben mit SQL-Anweisungen zu verketten, stellen Sie mithilfe von Parametern sicher, dass Eingaben nur als Literalwert behandelt und nie ausgeführt werden. In SQLite sind Parameter in der Regel überall dort zulässig, wo in SQL-Anweisungen Literalwerte zulässig sind.

Parametern können die Präfixe `:`, `@` oder `$` vorangestellt werden.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Weitere Informationen zur Zuordnung von .NET-Werten zu SQLite-Werten finden Sie unter [Datentypen](types.md).

## <a name="truncation"></a>Abschneiden

Verwenden Sie zum Abschneiden von TEXT- und BLOB-Werten die Eigenschaft <xref:Microsoft.Data.Sqlite.SqliteParameter.Size>.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Size = 30;
```

## <a name="alternative-types"></a>Alternative Typen

Möglicherweise sollten Sie ab und zu einen alternativen SQLite-Typ verwenden. Legen Sie dazu die Eigenschaft <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> fest.

Die folgende Zuordnung von alternativen Datentypen ist hierbei nützlich. Die Standardzuordnungen finden Sie unter [Datentypen](types.md).

| Wert          | SQLite-Typ | Hinweise          |
| -------------- | ---------- | ---------------- |
| Char           | Ganze Zahl    | UTF-16           |
| DateTime       | Real       | Wert für julianisches Datum |
| DateTimeOffset | Real       | Wert für julianisches Datum |
| GUID           | Blob       |                  |
| TimeSpan       | Real       | In Tagen          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>Ausgabeparameter

Ausgabeparameter werden von SQLite nicht unterstützt. Geben Sie stattdessen Werte in den Abfrageergebnissen zurück.

## <a name="see-also"></a>Siehe auch

* [Datentypen](types.md)
