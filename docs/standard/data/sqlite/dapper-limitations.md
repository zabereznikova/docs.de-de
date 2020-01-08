---
title: Dappereinschränkungen
ms.date: 12/13/2019
description: Beschreibt einige der Einschränkungen, die bei der Verwendung von dapperauftreten werden.
ms.openlocfilehash: 90c7fb24f068d663081390bdba9b1b222b4be56e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450495"
---
# <a name="dapper-limitations"></a>Dappereinschränkungen

Es gibt einige Einschränkungen, die Sie beachten sollten, wenn Sie Microsoft. Data. sqlite mit [dapperverwenden](https://stackexchange.github.io/Dapper/).

## <a name="parameters"></a>Parameters

Bei sqlite-Parameternamen wird Groß-/Kleinschreibung beachtet Stellen Sie sicher, dass die in SQL verwendeten Parameternamen der Groß-/Kleinschreibung der Eigenschaften des anonymen Objekts entsprechen. Problem [#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) würde diese Vorgehensweise verbessern.

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
