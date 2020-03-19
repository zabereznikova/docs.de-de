---
title: Parameter
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie SQL-Parameter verwenden.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401202"
---
# <a name="parameters"></a>Parameter

Parameter werden zum Schutz vor SQL-Injektionsangriffen verwendet. Anstatt Benutzereingaben mit SQL-Anweisungen zu verketten, verwenden Sie Parameter, um sicherzustellen, dass Die Eingabe immer nur als Literalwert behandelt und nie ausgeführt wird. In SQLite sind Parameter in der Regel überall dort zulässig, wo ein Literal in SQL-Anweisungen zulässig ist.

Parametern kann entweder `:`, `@`oder `$`vorangestellt werden.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Weitere Informationen dazu, wie .NET-Werte SQLite-Werten zugeordnet werden, finden Sie unter [Datentypen.](types.md)

## <a name="truncation"></a>Abschneiden

Verwenden <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> Sie die Eigenschaft, um TEXT- und BLOB-Werte abzurunden.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>Alternative Typen

Manchmal möchten Sie möglicherweise einen alternativen SQLite-Typ verwenden. Geben Sie hierzu die <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> Eigenschaft fest.

Die folgenden alternativen Typzuordnungen können verwendet werden. Informationen zu den Standardzuordnungen finden Sie unter [Datentypen](types.md).

| value          | SqliteType | Bemerkungen          |
| -------------- | ---------- | ---------------- |
| Char           | Integer    | UTF-16           |
| Datetime       | Real       | Julianer Tageswert |
| DateTimeOffset | Real       | Julianer Tageswert |
| Guid           | Blob       |                  |
| TimeSpan       | Real       | In Tagen          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>Ausgabeparameter

SQLite unterstützt keine Ausgabeparameter. Geben Sie stattdessen Werte in den Abfrageergebnissen zurück.

## <a name="see-also"></a>Weitere Informationen

* [Datentypen](types.md)
