---
title: Benutzerdefinierte Funktionen
ms.date: 12/13/2019
description: Hier erfahren Sie, wie Sie benutzerdefinierte Skalar- und Aggregatfunktionen erstellen.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450411"
---
# <a name="user-defined-functions"></a>Benutzerdefinierte Funktionen

Die meisten Datenbanken nutzen einen prozeduralen Dialekt von SQL, mit dem Sie eigene Funktionen definieren können. SQLite wird jedoch prozessintern mit ihrer App ausgeführt. Anstatt einen neuen Dialekt von SQL erlernen zu müssen, können Sie einfach die Programmiersprache Ihrer App verwenden.

## <a name="scalar-functions"></a>Skalarfunktionen

Skalarfunktionen geben einen einzelnen Skalarwert für jede Zeile in einer Abfrage zurück. Definieren Sie mithilfe von <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A> neue Skalarfunktionen, und überschreiben Sie die integrierten.

Eine Liste der unterstützten Parameter und Rückgabetypen für das `func`-Argument finden Sie unter [Datentypen](types.md).

Wenn Sie das `state`-Argument angeben, wird dieser Wert an jeden Aufruf der Funktion übergeben. Verwenden Sie dieses, um Abschlüsse zu vermeiden.

Geben Sie `isDeterministic` an, wenn Ihre Funktion deterministisch ist, damit SQLite bei der Kompilierung von Abfragen zusätzliche Optimierungen anwenden kann.

Im folgenden Beispiel wird gezeigt, wie Sie eine Skalarfunktion hinzufügen, um den Radius eines Zylinders zu berechnen.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a>Operatoren

Die folgenden SQLite-Operatoren werden durch entsprechende Skalarfunktionen implementiert. Wenn Sie diese Skalarfunktionen in Ihrer App definieren, wird das Verhalten dieser Operatoren überschrieben.

| Operator          | Funktion      |
| ----------------- | ------------- |
| X GLOB Y          | glob(Y, X)    |
| X LIKE Y          | like(Y, X)    |
| X LIKE Y ESCAPE Z | like(Y, X, Z) |
| X MATCH Y         | match(Y, X)   |
| X REGEXP Y        | regexp(Y, X)  |

Im folgenden Beispiel wird veranschaulicht, wie die RegEx-Funktion definiert wird, um den entsprechenden Operator zu aktivieren. SQLite enthält keine Standardimplementierung der RegEx-Funktion.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a>Aggregatfunktionen

Aggregatfunktionen geben einen einzelnen aggregierten Wert für alle Zeilen in einer Abfrage zurück. Definieren und überschreiben Sie Aggregatfunktionen mithilfe von <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.

Das `seed`-Argument gibt den ursprünglichen Zustand des Kontexts an. Verwenden Sie dieses auch, um Abschlüsse zu vermeiden.

Das `func`-Argument wird einmal pro Zeile aufgerufen. Verwenden Sie den Kontext, um ein Endergebnis zu akkumulieren. Geben Sie den Kontext zurück. Mit diesem Muster ist es möglich, dass der Kontext oder ein Werttyp unveränderlich wird.

Wenn `resultSelector` nicht angegeben wird, wird der endgültige Zustand des Kontexts als Ergebnis verwendet. Dadurch kann die Definition von Funktionen wie sum und count vereinfacht werden, die jeweils nur eine Zahl für jede Zeile erhöhen und zurückgeben müssen.

Geben Sie `resultSelector` an, um das Endergebnis aus dem Kontext zu berechnen, nachdem Sie alle Zeilen durchlaufen haben.

Eine Liste der unterstützten Parameter für das `func`-Argument und der Rückgabetypen für `resultSelector` finden Sie unter [Datentypen](types.md).

Geben Sie `isDeterministic` an, wenn Ihre Funktion deterministisch ist, damit SQLite bei der Kompilierung von Abfragen zusätzliche Optimierungen anwenden kann.

Im folgenden Beispiel wird eine Aggregatfunktion definiert, um die Standardabweichung einer Spalte zu berechnen.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a>Fehler

Wenn eine benutzerdefinierte Funktion eine Ausnahme auslöst, wird die Meldung an SQLite zurückgegeben. SQLite löst dann einen Fehler aus, und Microsoft.Data.Sqlite löst eine SqliteException-Ausnahme aus. Weitere Informationen finden Sie unter [Datenbankfehler](database-errors.md).

Standardmäßig lautet der SQLite-Fehlercode SQLITE_ERROR (oder 1). Sie können diesen jedoch ändern, indem Sie eine <xref:Microsoft.Data.Sqlite.SqliteException>-Ausnahme in ihrer Funktion mit dem gewünschten <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode>-Fehlercode auslösen.

## <a name="debugging"></a>Debuggen

SQLite ruft Ihre Implementierung direkt auf. Auf diese Weise können Sie Breakpoints hinzufügen, die beim Auswerten von Abfragen durch SQLite auslöst werden. Die vollständige .NET-Debuggingfunktion ist verfügbar, um Sie beim Erstellen benutzerdefinierter Funktionen zu unterstützen.

## <a name="see-also"></a>Siehe auch

* [Datentypen](types.md)
* [SQLite-Kernfunktionen](https://www.sqlite.org/lang_corefunc.html)
* [SQLite-Aggregatfunktionen](https://www.sqlite.org/lang_aggfunc.html)
