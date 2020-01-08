---
title: Parameters
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie SQL-Parameter verwenden.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450423"
---
# <a name="parameters"></a>Parameters

Parameter werden zum Schutz vor Einschleusung von SQL-Befehlen verwendet. Anstatt Benutzereingaben mit SQL-Anweisungen zu verketten, verwenden Sie Parameter, um sicherzustellen, dass die Eingabe nur als Literalwert behandelt und nie ausgeführt wird. In SQLite sind Parameter in der Regel überall zulässig, wo ein Literalwert in SQL-Anweisungen zulässig ist.

Parametern kann entweder `:`, `@`oder `$`vorangestellt werden.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Ausführliche Informationen dazu, wie .net-Werte SQLite-Werten zugeordnet werden, finden Sie unter [Datentypen](types.md) .

## <a name="truncation"></a>Abschneiden

Verwenden Sie die <xref:Microsoft.Data.Sqlite.SqliteParameter.Size>-Eigenschaft, um Text-und BLOB-Werte abzuschneiden.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>Alternative Typen

Manchmal möchten Sie möglicherweise einen alternativen SQLite-Typ verwenden. Legen Sie hierzu die <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>-Eigenschaft fest.

Die folgenden alternativen Typmappings können verwendet werden. Die Standard Zuordnungen finden Sie unter [Datentypen](types.md).

| {2&gt;Wert&lt;2}          | Sqlitetype | Hinweise          |
| -------------- | ---------- | ---------------- |
| Char           | Ganze Zahl    | UTF-16           |
| DateTime       | Real       | Wert des Julianischen Tags |
| DateTimeOffset | Real       | Wert des Julianischen Tags |
| GUID           | Blob       |                  |
| TimeSpan       | Real       | In Tagen          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>Ausgabeparameter

SQLite unterstützt keine Ausgabeparameter. Geben Sie stattdessen Werte in den Abfrage Ergebnissen zurück.

## <a name="see-also"></a>Siehe auch

* [Datentypen](types.md)
