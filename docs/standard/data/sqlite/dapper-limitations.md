---
title: Dappereinschränkungen
ms.date: 12/13/2019
description: Beschreibt einige der Einschränkungen, die bei der Verwendung von dapperauftreten werden.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901199"
---
# <a name="dapper-limitations"></a>Dappereinschränkungen

Es gibt einige Einschränkungen, die Sie beachten sollten, wenn Sie Microsoft. Data. sqlite mit [dapperverwenden](https://stackexchange.github.io/Dapper/).

## <a name="parameters"></a>Parameters

Bei sqlite-Parameternamen wird Groß-/Kleinschreibung beachtet Stellen Sie sicher, dass die in SQL verwendeten Parameternamen der Groß-/Kleinschreibung der Eigenschaften des anonymen Objekts entsprechen. Problem [#18861](https://github.com/dotnet/efcore/issues/18861) würde diese Vorgehensweise verbessern.

Dappererwartet auch, dass Parameter das `@` Präfix verwenden. Andere Präfixe funktionieren nicht.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a>Datentypen

Dapperliest Werte mithilfe des sqlitedatareader-Indexers. Der Rückgabetyp dieses Indexers ist Object, d. h., es werden nur die Werte Long, Double, String oder Byte [] zurückgegeben. Weitere Informationen finden Sie unter [Datentypen](types.md). Dapperverarbeitet die meisten Konvertierungen zwischen diesen und anderen primitiven Typen. Leider werden `DateTimeOffset`, `Guid`oder `TimeSpan`nicht behandelt. Erstellen Sie Typhandler, wenn Sie diese Typen in ihren Ergebnissen verwenden möchten.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

Vergessen Sie nicht, die Typhandler vor der Abfrage hinzuzufügen.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a>Siehe auch

* [Datentypen](types.md)
* [Async-Einschränkungen](async.md)
