---
title: Datentypen
ms.date: 12/13/2019
description: Beschreibt die unterstützten Datentypen und einige der damit Zusammenhang geltenden Einschränkungen.
ms.openlocfilehash: ae70cb91a5a6d9cfed45a5a47dda25a70362871e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450417"
---
# <a name="data-types"></a>Datentypen

SQLite verfügt nur über vier primitive Datentypen: Integer, Real, Text und BLOB. APIs, die Daten Bankwerte als `object` zurückgeben, werden nur einen dieser vier Typen zurückgeben. Zusätzliche .NET-Typen werden von Microsoft. Data. sqlite unterstützt, aber die Werte werden letztendlich zwischen diesen Typen und einem der vier primitiven Typen umgewandelt.

| .NET           | SQLite  | Hinweise                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolean        | INTEGER | `0` oder `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | yyyy-mm-dd hh: mm: SS. FFFFFFF                                   |
| DateTimeOffset | TEXT    | yyyy-mm-dd hh: mm: SS. Fffffffzzz                                |
| Decimal        | TEXT    | `0.0###########################`-Format. "Real" wäre "Lossy". |
| Double         | REAL    |                                                               |
| GUID           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Einmaliges         | REAL    |                                                               |
| Zeichenfolge         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d. hh: mm: SS. fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt64         | INTEGER | Überlauf bei großen Werten                                         |

## <a name="alternative-types"></a>Alternative Typen

Einige .NET-Typen können aus alternativen SQLite-Typen gelesen werden. Parameter können auch so konfiguriert werden, dass diese alternativen Typen verwendet werden. Weitere Informationen finden Sie unter [Parameter](parameters.md#alternative-types).

| .NET           | SQLite  | Hinweise          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | REAL    | Wert des Julianischen Tags |
| DateTimeOffset | REAL    | Wert des Julianischen Tags |
| GUID           | BLOB    |                  |
| TimeSpan       | REAL    | In Tagen          |

Beispielsweise liest die folgende Abfrage einen TimeSpan-Wert aus einer realen Spalte im Resultset.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Spaltentypen

SQLite verwendet ein dynamisches Typsystem, bei dem der Typ eines Werts dem Wert selbst und nicht der Spalte zugeordnet ist, in der er gespeichert ist. Sie können den gewünschten Spaltentypen Namen verwenden. Microsoft. Data. sqlite wendet keine zusätzliche Semantik auf diese Namen an.

Der Spaltentyp Name wirkt sich auf die [typaffinität](https://www.sqlite.org/datatype3.html#type_affinity)aus. Ein gängiges Problem besteht darin, dass durch die Verwendung eines Spalten Typs der Zeichenfolge versucht wird, Werte in Integer oder Real zu konvertieren, was zu unerwarteten Ergebnissen führen kann. Es wird empfohlen, nur die vier primitiven SQLite-Typnamen zu verwenden: Integer, Real, Text und BLOB.

SQLite ermöglicht Ihnen das Angeben von typfacetten, wie z. b. Länge, Genauigkeit und Dezimalstellen, die jedoch nicht von der Datenbank-Engine erzwungen werden. Ihre APP ist dafür verantwortlich, diese zu erzwingen.

## <a name="see-also"></a>Siehe auch

- [Datatypes in SQLite](https://www.sqlite.org/datatype3.html)
