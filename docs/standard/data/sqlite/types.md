---
title: Datentypen
ms.date: 12/13/2019
description: In diesem Artikel werden die unterstützten Datentypen und einige der dafür geltenden Einschränkungen beschrieben.
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389040"
---
# <a name="data-types"></a>Datentypen

SQLite verfügt nur über vier primitive Datentypen: INTEGER, REAL, TEXT und BLOB. APIs, die Datenbankwerte als `object` zurückgeben, geben immer nur einen dieser vier Typen zurück. Weitere .NET-Typen werden zwar von Microsoft.Data.Sqlite unterstützt, aber die Werte werden letztendlich von diesen Typen in einen der vier primitiven Typen umgewandelt.

| .NET           | SQLite  | Hinweise                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolesch        | INTEGER | `0` oder `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | yyyy-MM-dd HH:mm:ss.FFFFFFF                                   |
| DateTimeOffset | TEXT    | yyyy-MM-dd HH:mm:ss.FFFFFFFzzz                                |
| Decimal        | TEXT    | Das verwendete Format ist `0.0###########################`. REAL wäre verlustbehaftet. |
| Double         | real    |                                                               |
| GUID           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | real    |                                                               |
| Zeichenfolge         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d.hh:mm:ss.fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt32         | INTEGER |                                                               |
| UInt64         | INTEGER | Überlauf bei großen Werten                                         |

## <a name="alternative-types"></a>Alternative Typen

Einige .NET-Typen können auch als andere SQLite-Typen gelesen werden. Parameter können auch so konfiguriert werden, dass diese alternativen Typen verwendet werden. Weitere Informationen finden Sie unter [Parameter](parameters.md#alternative-types).

| .NET           | SQLite  | Hinweise          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | real    | Wert für julianischen Tag |
| DateTimeOffset | real    | Wert für julianischen Tag |
| GUID           | BLOB    |                  |
| TimeSpan       | real    | In Tagen          |

Die folgende Abfrage liest beispielsweise einen TimeSpan-Wert aus einer REAL-Spalte im Resultset.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Spaltentypen

SQLite verwendet ein dynamisches Typsystem, bei dem der Typ eines Werts dem Wert selbst und nicht der Spalte zugeordnet ist, in der er gespeichert ist. Sie können beliebige Spaltentypnamen verwenden. Microsoft.Data.Sqlite wendet keine zusätzliche Semantik auf diese Namen an.

Der Spaltentypname wirkt sich allerdings auf die [Typaffinität](https://www.sqlite.org/datatype3.html#type_affinity) aus. Ein häufig auftretendes Problem besteht darin, dass bei Verwendung des Spaltentyps STRING versucht wird, die Werte in die Datentypen INTEGER oder REAL umzuwandeln, was zu unerwarteten Ergebnissen führen kann. Es wird empfohlen, nur die vier primitiven SQLite-Typnamen zu verwenden: INTEGER, REAL, TEXT und BLOB.

SQLite ermöglicht Ihnen das Angeben von Facets für Typen (z. B. Länge, Genauigkeit und Größe), die jedoch nicht von der Datenbank-Engine erzwungen werden. Ihre App ist dafür verantwortlich, diese zu erzwingen.

## <a name="see-also"></a>Siehe auch

- [Datentypen in SQLite](https://www.sqlite.org/datatype3.html)
