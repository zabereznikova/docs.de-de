---
title: Datentypen
ms.date: 12/13/2019
description: Beschreibt die unterstützten Datentypen und einige der Einschränkungen, die sie umgibt.
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389040"
---
# <a name="data-types"></a>Datentypen

SQLite verfügt nur über vier primitive Datentypen: INTEGER, REAL, TEXT und BLOB. APIs, die Datenbankwerte `object` als einen zurückgeben, geben immer nur einen dieser vier Typen zurück. Zusätzliche .NET-Typen werden von Microsoft.Data.Sqlite unterstützt, aber Werte werden letztendlich zwischen diesen Typen und einem der vier primitiven Typen genötigt.

| .NET           | SQLite  | Bemerkungen                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolean        | INTEGER | `0` oder `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| Datetime       | TEXT    | yyyy-MM-dd HH:mm:ss. FFFFFFF                                   |
| DateTimeOffset | TEXT    | yyyy-MM-dd HH:mm:ss. FFFFFzzz                                |
| Decimal        | TEXT    | `0.0###########################`Format. REAL wäre verlustbehaftet. |
| Double         | real    |                                                               |
| Guid           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | real    |                                                               |
| String         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d.hh:mm:ss.fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt32         | INTEGER |                                                               |
| UInt64         | INTEGER | Große Werte überlaufen                                         |

## <a name="alternative-types"></a>Alternative Typen

Einige .NET-Typen können aus alternativen SQLite-Typen gelesen werden. Parameter können auch für die Verwendung dieser alternativen Typen konfiguriert werden. Weitere Informationen finden Sie unter [Parameter](parameters.md#alternative-types).

| .NET           | SQLite  | Bemerkungen          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| Datetime       | real    | Julianer Tageswert |
| DateTimeOffset | real    | Julianer Tageswert |
| Guid           | BLOB    |                  |
| TimeSpan       | real    | In Tagen          |

Die folgende Abfrage liest z. B. einen TimeSpan-Wert aus einer REAL-Spalte im Resultset.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Spaltentypen

SQLite verwendet ein dynamisches Typsystem, bei dem der Typ eines Werts dem Wert selbst zugeordnet ist und nicht der Spalte, in der er gespeichert ist. Es steht Ihnen frei, den gewünschten Spaltentypnamen zu verwenden. Microsoft.Data.Sqlite wendet keine zusätzliche Semantik auf diese Namen an.

Der Spaltentypname wirkt sich auf die [Typaffinität](https://www.sqlite.org/datatype3.html#type_affinity)aus. Eine häufige gotcha ist, dass die Verwendung eines Spaltentyps von STRING versucht, Werte in INTEGER oder REAL zu konvertieren, was zu unerwarteten Ergebnissen führen kann. Es wird empfohlen, nur die vier primitiven SQLite-Typnamen zu verwenden: INTEGER, REAL, TEXT und BLOB.

Mit SQLite können Sie Typfacetten wie Länge, Genauigkeit und Skalierung angeben, die jedoch nicht vom Datenbankmodul erzwungen werden. Ihre App ist für deren Durchsetzung verantwortlich.

## <a name="see-also"></a>Weitere Informationen

- [Datentypen in SQLite](https://www.sqlite.org/datatype3.html)
