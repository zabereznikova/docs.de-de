---
title: Dapper-Einschränkungen
ms.date: 12/13/2019
description: In diesem Artikel werden einige Einschränkungen bei der Verwendung von Dapper beschrieben.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901199"
---
# <a name="dapper-limitations"></a>Dapper-Einschränkungen

Es gibt ein paar Einschränkungen, die Sie beachten sollten, wenn Sie Microsoft.Data.Sqlite mit [Dapper](https://stackexchange.github.io/Dapper/)verwenden.

## <a name="parameters"></a>Parameter

Bei SQLite-Parameternamen wird die Groß-/Kleinschreibung beachtet. Stellen Sie sicher, dass bei den in SQL verwendeten Parameternamen die Groß-/Kleinschreibung mit der der Eigenschaften des anonymen Objekts übereinstimmt. Durch Issue [18861](https://github.com/dotnet/efcore/issues/18861) konnte dieses Verhalten optimiert werden.

Dapper erwartet auch, dass Parameter das Präfix `@` verwenden. Andere Präfixe funktionieren nicht.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a>Datentypen

Dapper liest Werte mithilfe des SqliteDataReader-Indexers. Der Rückgabetyp dieses Indexers ist Objekt. Das bedeutet, es werden nur Werte vom Typ long, double, string oder byte[] zurückgegeben. Weitere Informationen finden Sie unter [Datentypen](types.md). Dapper führt die meisten der Konvertierungen zwischen diesen und anderen primitiven Typen durch. Leider werden `DateTimeOffset`, `Guid` und `TimeSpan` nicht verwendet. Erstellen Sie Typhandler, wenn Sie diese Typen in Ihren Ergebnissen verwenden möchten.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

Vergessen Sie nicht, die Typhandler vor der Abfrage hinzuzufügen.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a>Siehe auch

* [Datentypen](types.md)
* [Async-Einschränkungen](async.md)
