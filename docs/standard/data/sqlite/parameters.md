---
title: Parameter
ms.date: 12/13/2019
description: Hier erfahren Sie mehr über die Verwendung von SQL-Parametern.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401202"
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
command.Parameters.AddWithValue("$name", name).Length = 30;
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
