---
title: 'Ressourcenverwaltung: Das use-Schlüsselwort'
description: Erfahren Sie mehr F# über das Schlüsselwort "Use" und die Funktion "using", die die Initialisierung und Freigabe von Ressourcen steuern können.
ms.date: 05/16/2016
ms.openlocfilehash: 5e0838401bee02050343b2f6dcc646a8dc8b4dc0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627260"
---
# <a name="resource-management-the-use-keyword"></a>Ressourcenverwaltung: Das use-Schlüsselwort

In diesem Thema werden das `use` -Schlüssel `using` Wort und die-Funktion beschrieben, die die Initialisierung und Freigabe von Ressourcen steuern können.

## <a name="resources"></a>Ressourcen

Der Begriff " *Resource* " wird auf mehr als eine Weise verwendet. Ja, Ressourcen können Daten sein, die von einer Anwendung verwendet werden, z. b. Zeichen folgen, Grafiken und ähnliches, aber in diesem Kontext bezieht sich der *Ressourcen* auf Software-oder Betriebssystemressourcen, z. b. Grafikgeräte Kontexte, Datei Handles, Netzwerk und Datenbank. Verbindungen, Parallelitäts Objekte, wie z. b. Wait-Handles, usw. Die Verwendung dieser Ressourcen durch Anwendungen umfasst die Beschaffung der Ressource vom Betriebssystem oder von einem anderen Ressourcenanbieter, gefolgt von der späteren Freigabe der Ressource zum Pool, damit Sie für eine andere Anwendung bereitgestellt werden kann. Es treten Probleme auf, wenn Anwendungen Ressourcen nicht wieder in den gemeinsamen Pool freigeben.

## <a name="managing-resources"></a>Verwalten von Ressourcen

Zur effizienten und verantwortungsvollen Verwaltung von Ressourcen in einer Anwendung müssen Sie Ressourcen umgehend und auf vorhersagbare Weise freigeben. Der .NET Framework unterstützt Sie durch die Bereitstellung `System.IDisposable` der-Schnittstelle. Ein Typ, der `System.IDisposable` implementiert, `System.IDisposable.Dispose` verfügt über die-Methode, die Ressourcen ordnungsgemäß freigibt. Gut geschriebene Anwendungen garantieren, dass `System.IDisposable.Dispose` umgehend aufgerufen wird, wenn ein Objekt, das eine begrenzte Ressource enthält, nicht mehr benötigt wird. Glücklicherweise unterstützen die meisten zur Vereinfachung und F# ist keine Ausnahme. Es gibt zwei nützliche Sprachkonstrukte, die das Lösch Muster unter `use` stützen: die `using` -Bindung und die-Funktion.

## <a name="use-binding"></a>Bindung verwenden

Das `use` -Schlüsselwort weist ein Formular `let` auf, das der-Bindung ähnelt:

*Ausdruck* " *Wert* = verwenden"

Sie bietet die gleiche Funktionalität wie eine `let` Bindung, fügt aber einen- `Dispose` Rückruf für den Wert hinzu, wenn der Wert den Gültigkeitsbereich verlässt. Beachten Sie, dass der Compiler eine NULL-Überprüfung für den Wert einfügt, sodass der `null` `Dispose` -Vorgang nicht versucht wird, wenn der Wert ist.

Im folgenden Beispiel wird gezeigt, wie eine Datei automatisch mit dem `use` -Schlüsselwort geschlossen wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> Sie können in `use` Berechnungs Ausdrücken verwenden. in diesem Fall wird eine angepasste Version `use` des Ausdrucks verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md)und [Berechnungs Ausdrücke](computation-expressions.md).

## <a name="using-function"></a>using-Funktion

Die `using` Funktion hat die folgende Form:

`using`(*expression1*) *Function-or-Lambda*

In einem `using` -Ausdruck erstellt *expression1* das-Objekt, das verworfen werden muss. Das Ergebnis von *expression1* (das-Objekt, das verworfen werden muss) wird zu einem Argument, einem *Wert*, einer *Funktion oder einem Lambda*, das entweder eine Funktion ist, die ein einzelnes verbleibendes Argument eines Typs erwartet, das mit dem Wert übereinstimmt, der von *erzeugt wurde. expression1*oder ein Lambda-Ausdruck, der ein Argument dieses Typs erwartet. Am Ende der Ausführung der Funktion ruft `Dispose` die Laufzeit die Ressourcen auf und gibt Sie frei (es sei denn, der Wert ist `null`. in diesem Fall wird der Aufruf von "verwerfen" nicht versucht).

Im folgenden Beispiel wird der `using` Ausdruck mit einem Lambda-Ausdruck veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

Das nächste Beispiel zeigt den `using` -Ausdruck mit einer-Funktion.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

Beachten Sie, dass die Funktion eine Funktion sein kann, für die bereits einige Argumente angewendet wurden. Dies wird im folgenden Codebeispiel veranschaulicht. Es wird eine Datei erstellt, die die `XYZ`Zeichenfolge enthält.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

Die `using` -Funktion und `use` die-Bindung sind nahezu gleichwertig, um das gleiche zu erreichen. Das `using` -Schlüsselwort bietet mehr Kontrolle `Dispose` darüber, wenn aufgerufen wird. Wenn Sie verwenden `using`, `Dispose` wird am Ende der Funktion oder des Lambda Ausdrucks aufgerufen. Wenn Sie das `use` Schlüsselwort verwenden, `Dispose` wird am Ende des enthaltenden Codeblocks aufgerufen. Im Allgemeinen empfiehlt es sich, anstelle `use` `using` der-Funktion zu verwenden.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
