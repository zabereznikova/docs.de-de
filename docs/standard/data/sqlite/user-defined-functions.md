---
title: Benutzerdefinierte Funktionen
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie benutzerdefinierte skalare und Aggregatfunktionen erstellen.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450411"
---
# <a name="user-defined-functions"></a>Benutzerdefinierte Funktionen

Die meisten Datenbanken verfügen über einen prozeduralen Dialekt von SQL, den Sie verwenden können, um eigene Funktionen zu definieren. SQLite wird jedoch in-Process mit ihrer app ausgeführt. Anstatt einen neuen Dialekt von SQL erlernen zu müssen, können Sie einfach die Programmiersprache Ihrer APP verwenden.

## <a name="scalar-functions"></a>Skalarfunktionen

Skalare Funktionen geben einen einzelnen Skalarwert für jede Zeile in einer Abfrage zurück. Definieren Sie neue Skalarfunktionen, und überschreiben Sie die integrierten, indem Sie <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>verwenden.

Eine Liste der unterstützten Parameter und Rückgabe Typen für das `func`-Argument finden Sie unter [Datentypen](types.md) .

Wenn Sie das `state`-Argument angeben, wird dieser Wert an jeden Aufruf der Funktion übergeben. Verwenden Sie dies, um Abschlüsse zu vermeiden.

Geben Sie `isDeterministic` an, wenn ihre Funktion deterministisch ist, damit SQLite bei der Kompilierung von Abfragen zusätzliche Optimierungen verwenden kann.

Im folgenden Beispiel wird gezeigt, wie Sie eine Skalarfunktion hinzufügen, um den Radius eines Zylinders zu berechnen.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a>Operatoren

Die folgenden SQLite-Operatoren werden durch entsprechende Skalarfunktionen implementiert. Wenn Sie diese Skalarfunktionen in Ihrer APP definieren, wird das Verhalten dieser Operatoren überschrieben.

| Operator          | Funktion      |
| ----------------- | ------------- |
| X-glob-Y          | glob (Y, X)    |
| X wie Y          | Like (Y, X)    |
| X wie Y Escape Z | Like (Y, X, Z) |
| X-Treffer Y         | Match (Y, X)   |
| X regexp Y        | RegExp (Y, X)  |

Im folgenden Beispiel wird gezeigt, wie die regexp-Funktion definiert wird, um den entsprechenden-Operator zu aktivieren. SQLite schließt keine Standard Implementierung der RegExp-Funktion ein.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a>Aggregatfunktionen

Aggregatfunktionen geben einen einzelnen aggregierten Wert für alle Zeilen in einer Abfrage zurück. Definieren und Überschreiben von Aggregatfunktionen mit <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.

Das `seed`-Argument gibt den ursprünglichen Zustand des Kontexts an. Verwenden Sie diese Informationen, um auch keine Abschlüsse zu vermeiden.

Das `func`-Argument wird einmal pro Zeile aufgerufen. Verwenden Sie den Kontext, um ein endgültiges Ergebnis zu sammeln. Gibt den Kontext zurück. Mit diesem Muster kann der Kontext ein Werttyp oder unveränderlich sein.

Wenn keine `resultSelector` angegeben wird, wird der endgültige Zustand des Kontexts als Ergebnis verwendet. Dies kann die Definition von Funktionen wie Sum und count vereinfachen, die jeweils nur eine Zahl für jede Zeile erhöhen und zurückgeben müssen.

Geben Sie `resultSelector` an, um das Endergebnis aus dem Kontext zu berechnen, nachdem Sie alle Zeilen durchlaufen haben.

Eine Liste der unterstützten Parametertypen für das `func` Argument und Rückgabe Typen für `resultSelector`finden Sie unter [Datentypen](types.md) .

Wenn Ihre Funktion deterministisch ist, geben Sie `isDeterministic` an, damit SQLite bei der Kompilierung von Abfragen zusätzliche Optimierungen verwenden kann.

Im folgenden Beispiel wird eine Aggregatfunktion definiert, um die Standardabweichung einer Spalte zu berechnen.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a>-Fehler

Wenn eine benutzerdefinierte Funktion eine Ausnahme auslöst, wird die Nachricht an SQLite zurückgegeben. SQLite löst dann einen Fehler aus, und Microsoft. Data. sqlite löst eine sqliteexception aus. Weitere Informationen finden Sie unter [Datenbankfehler](database-errors.md).

Standardmäßig ist der Fehler SQLite-Fehlercode SQLITE_ERROR (oder 1). Sie können Sie jedoch ändern, indem Sie eine <xref:Microsoft.Data.Sqlite.SqliteException> in ihrer Funktion mit dem gewünschten <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> auslösen.

## <a name="debugging"></a>Debugging

SQLite ruft Ihre Implementierung direkt auf. Auf diese Weise können Sie Haltepunkte hinzufügen, die beim Auswerten von Abfragen durch SQLite auslöst werden. Die vollständige .net-Debuggingfunktion ist verfügbar, um Sie beim Erstellen benutzerdefinierter Funktionen zu unterstützen.

## <a name="see-also"></a>Siehe auch

* [Datentypen](types.md)
* [SQLite Core-Funktionen](https://www.sqlite.org/lang_corefunc.html)
* [SQLite-Aggregatfunktionen](https://www.sqlite.org/lang_aggfunc.html)
