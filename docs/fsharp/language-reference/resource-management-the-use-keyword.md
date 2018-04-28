---
title: 'Ressourcenverwaltung: Das use-Schlüsselwort (F#)'
description: Informationen Sie zu F#-Schlüsselwort "Use" und die 'using'-Funktion, die die Initialisierung und Freigabe von Ressourcen steuern kann.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0e134bf5b302911324dd224316941fee693b787b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="resource-management-the-use-keyword"></a>Ressourcenverwaltung: Das use-Schlüsselwort

In diesem Thema wird beschrieben, das Schlüsselwort `use` und die `using` -Funktion, die die Initialisierung und Freigabe von Ressourcen steuern kann.

## <a name="resources"></a>Ressourcen
Der Begriff *Ressource* auf mehr als eine Art verwendet wird. Ja, Ressourcen Daten, die eine Anwendung z. B. Zeichenfolgen, Grafiken und ähnliche, aber in diesem Kontext verwendet werden können *Ressourcen* bezieht sich auf Software oder Betriebssystem-Ressourcen, z. B. Grafiken Gerätekontexte, Dateihandles, Netzwerk und Datenbank-Verbindungen, Parallelitätsobjekten z. B. Wait-Handles und So weiter. Die Verwendung dieser Ressourcen durch Anwendungen umfasst die Übernahme von der Ressource mit dem das Betriebssystem oder anderen Ressourcenanbieter, gefolgt von die höhere Version der Ressource an den Pool, sodass es für eine andere Anwendung bereitgestellt werden kann. Probleme auftreten, wenn Anwendungen nicht die Ressourcen für den gemeinsamen Pool wieder freigeben.

## <a name="managing-resources"></a>Verwalten von Ressourcen
Zum Verwalten von effizient und bittet Ressourcen in einer Anwendung, müssen Sie sofort und in einer vorhersagbaren Weise Ressourcen freigeben. .NET Framework können Sie dies tun, indem Sie die Bereitstellung der `System.IDisposable` Schnittstelle. Ein Typ, der implementiert `System.IDisposable` hat die `System.IDisposable.Dispose` -Methode, die Ressourcen korrekt freigegeben. Gut geschriebene Anwendungen sicherstellen, dass `System.IDisposable.Dispose` wird sofort aufgerufen, wenn jedes Objekt, das eine eingeschränkte Ressource ist nicht mehr benötigt wird. Glücklicherweise unterstützen die meisten zur Vereinfachung und f# stellt keine Ausnahme. Es gibt zwei hilfreiche Sprachkonstrukte, die das Dispose-Muster unterstützen: die `use` Bindung und die `using` Funktion.

## <a name="use-binding"></a>Verwenden der Bindung
Die `use` -Schlüsselwort hat ein Formular, das der ähnelt der `let` Bindung:

Verwenden Sie *Wert* = *Ausdruck*

Es bietet die gleiche Funktionalität wie ein `let` binden, jedoch Fügt einen Aufruf von `Dispose` auf den Wert, wenn der Wert den Gültigkeitsbereich verlässt. Beachten Sie, dass der Compiler Fügt eine null-Prüfung auf den Wert aus, damit, auch wenn der Wert ist `null`, den Aufruf von `Dispose` wird nicht ausgeführt.

Im folgende Beispiel wird gezeigt, wie eine Datei automatisch geschlossen werden mithilfe der `use` Schlüsselwort.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
Können Sie `use` im Berechnungsausdrücke, in diesem Fall, dass eine angepasste Version von den `use` Ausdruck verwendet wird. Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).


## <a name="using-function"></a>Mithilfe der Funktion
Die `using` Funktion weist folgende Form:

`using` (*expression1*) *-Funktion oder Lambda*

In einem `using` Ausdruck *expression1* erstellt das Objekt, das freigegeben werden muss. Das Ergebnis des *expression1* (das Objekt, das freigegeben werden muss), wird ein Argument *Wert*in *-Funktion oder Lambda*, dies ist entweder eine Funktion, die ein einzelnes erwartet von erzeugten verbleibende Argument des Typs, der den Wert entspricht *expression1*, oder einen Lambda-Ausdruck, der ein Argument dieses Typs erwartet. Am Ende der Ausführung der Funktion ruft die Runtime `Dispose` und die Ressourcen freigegeben werden (es sei denn, der Wert ist `null`, in diesem Fall der Aufruf von Dispose nicht versucht wird).

Das folgende Beispiel veranschaulicht die `using` Ausdruck mit einem Lambdaausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

Das folgende Beispiel zeigt die `using` Ausdruck mit einer Funktion.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

Beachten Sie, dass die Funktion eine Funktion handeln, die bereits einige Argumente angewendet wurde. Dies wird im folgenden Codebeispiel veranschaulicht. Erstellt eine Datei mit der Zeichenfolge `XYZ`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

Die `using` Funktion und die `use` Bindung sind nahezu äquivalente Verfahren, um dasselbe Ziel erreichen. Die `using` Schlüsselwort bietet mehr Kontrolle darüber, wann `Dispose` aufgerufen wird. Bei Verwendung von `using`, `Dispose` wird am Ende der Funktion oder einen Lambda-Ausdruck aufgerufen, wenn Sie mithilfe der `use` Schlüsselwort `Dispose` am Ende des enthaltenden Codeblocks aufgerufen wird. Im Allgemeinen sollten gewünscht verwenden `use` statt der `using` Funktion.


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)
