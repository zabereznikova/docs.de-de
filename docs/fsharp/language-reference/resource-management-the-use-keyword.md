---
title: 'Ressourcenverwaltung: Das Use-Schlüsselwort'
description: Erfahren Sie mehr über die F# 'verwendet'-Schlüsselwort und die "using"-Funktion, die die Initialisierung und Freigabe von Ressourcen steuern kann.
ms.date: 05/16/2016
ms.openlocfilehash: 127877a3823faade9bc3c6aefea655c86cc348e7
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613088"
---
# <a name="resource-management-the-use-keyword"></a>Ressourcenverwaltung: Das Use-Schlüsselwort

In diesem Thema wird beschrieben, das Schlüsselwort `use` und `using` -Funktion, die die Initialisierung und Freigabe von Ressourcen steuern kann.

## <a name="resources"></a>Ressourcen

Der Begriff *Ressource* auf mehr als eine Weise verwendet wird. Ja, Ressourcen können Daten, die eine Anwendung, z. B. Zeichenfolgen, Grafiken und ähnliches, aber in diesem Kontext verwendet werden *Ressourcen* bezieht sich auf Software oder Betriebssystem der Ressourcen, z. B. Grafiken Gerätekontexte, Dateihandles, Netzwerk und Verbindungen, Concurrency-Objekte, z. B. Wait-Handles und So weiter. Die Verwendung dieser Ressourcen durch Anwendungen beinhaltet die Übernahme des von der Ressource mit dem das Betriebssystem oder anderen Ressourcenanbieter, gefolgt von die höhere Version der Ressource, an den Pool, sodass es zu einer anderen Anwendung bereitgestellt werden kann. Probleme auftreten, wenn Anwendungen nicht die Ressourcen für den gemeinsamen Pool freigeben.

## <a name="managing-resources"></a>Verwalten von Ressourcen

Um effizient und bittet um Ressourcen in einer Anwendung verwalten, müssen Sie Ressourcen umgehend und in einer vorhersagbaren Weise freigeben. .NET Framework unterstützt dies durch die Bereitstellung der `System.IDisposable` Schnittstelle. Ein Typ, der implementiert `System.IDisposable` hat die `System.IDisposable.Dispose` -Methode, die korrekt Ressourcen freigibt. Gut geschriebene Anwendungen zu garantieren, dass `System.IDisposable.Dispose` wird sofort aufgerufen, wenn ein Objekt, das eine eingeschränkte Ressource enthält, nicht mehr benötigt wird. Glücklicherweise unterstützen die meisten zur Vereinfachung und F# ist keine Ausnahme. Es gibt zwei hilfreiche Sprachkonstrukte, die das Dispose-Muster unterstützen: die `use` Bindung und die `using` Funktion.

## <a name="use-binding"></a>Verwenden der Bindung

Die `use` -Schlüsselwort enthält ein Formular, das der ähnelt der `let` Bindung:

Verwenden Sie *Wert* = *Ausdruck*

Es bietet die gleiche Funktionalität wie eine `let` binden, aber Fügt einen Aufruf von `Dispose` auf dem Wert, wenn der Wert den Gültigkeitsbereich verlässt. Beachten Sie, dass der Compiler eine null-Überprüfung für den Wert und fügt, auch wenn der Wert lautet `null`, den Aufruf von `Dispose` nicht versucht wird.

Das folgende Beispiel zeigt, wie Sie eine Datei automatisch mit schließen die `use` Schlüsselwort.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> Können Sie `use` in Berechnungsausdrücken, in diesem Fall, dass eine angepasste Version von der `use` Ausdruck wird verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).

## <a name="using-function"></a>Mithilfe der Funktion

Die `using` Funktion hat folgende Form:

`using` (*expression1*) *-Funktion oder Lambda*

In einem `using` Ausdruck *expression1* erstellt das Objekt, das freigegeben werden muss. Das Ergebnis des *expression1* (das Objekt, das freigegeben werden muss), wird ein Argument, *Wert*zu *-Funktion oder Lambda*, dies ist entweder eine Funktion, die eine einzelne erwartet Verbleibende Argument des Typs, der den Wert entspricht erzeugten *expression1*, oder einen Lambda-Ausdruck, der ein Argument des Typs erwartet. Am Ende der Ausführung der Funktion, die Runtime ruft `Dispose` und die Ressourcen freigegeben werden (es sei denn, der Wert ist `null`, in diesem Fall der Aufruf von Dispose nicht versucht wird).

Das folgende Beispiel zeigt die `using` Ausdruck mit einem Lambda-Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

Das folgende Beispiel zeigt die `using` Ausdruck mit einer Funktion.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

Beachten Sie, dass die Funktion eine Funktion handeln, die bereits einige Argumente angewendet wurde. Dies wird im folgenden Codebeispiel veranschaulicht. Er erstellt eine Datei, die die Zeichenfolge enthält `XYZ`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

Die `using` Funktion und die `use` Bindung gibt nahezu gleichwertig Möglichkeiten, die den gleichen Zweck erfüllen. Die `using` Schlüsselwort bietet mehr Kontrolle darüber, wann `Dispose` aufgerufen wird. Bei Verwendung von `using`, `Dispose` wird am Ende der Funktion oder einen Lambda-Ausdruck aufgerufen, bei der Verwendung der `use` Schlüsselwort `Dispose` am Ende des enthaltenden Codeblocks aufgerufen wird. Im Allgemeinen sollten Sie lieber mit `use` statt der `using` Funktion.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)