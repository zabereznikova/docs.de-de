---
title: Werte
description: Erfahren Sie, wie Werte in F# Mengen sind, die einen bestimmten Typ aufweisen.
ms.date: 05/16/2016
ms.openlocfilehash: 5c1d4f1e59cbf092911d99a725654042bf3383b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902186"
---
# <a name="values"></a>Werte

Werte in F# sind Mengen, die einen bestimmten Typ aufweisen. Werte können Ganzzahlen oder Gleitkommazahlen, Zeichen oder Text, Listen, Sequenzen, Arrays, Tupeln, Unterscheidungs-Unions, Datensätze, Klassentypen oder Funktionswerte sein.

## <a name="binding-a-value"></a>Binden eines Werts

Der Begriff *Bindung* bezeichnet das Zuordnen eines Namens zu einer Definition. Das `let`-Schlüsselwort bindet einen Wert, wie in den folgenden Beispielen:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet601.fs)]

Der Typ eines Werts wird aus der Definition abgeleitet. Für einen primitiven Datentyp, z.B. eine Ganzzahl oder Gleitkommazahl, wird der Typ vom Typ des Literals bestimmt. Aus diesem Grund leitet der Compiler im vorherigen Beispiel den Typ `b` ab, um `unsigned int` zu sein, hingegen leitet der Compiler den Typ `a` ab, damit er `int` wird. Der Typ eines Funktionswerts wird anhand des Rückgabewerts im Funktionsrumpf bestimmt. Weitere Informationen über Funktionswerttypen finden Sie unter [Funktionen](../functions/index.md). Weitere Informationen über Literaltypen finden Sie unter [Literale](../literals.md).

Der Compiler gibt keine Diagnose zu nicht verwendeten Bindungen standardmäßig aus. Um diese Nachrichten erhalten, aktivieren Warnung 1182 in der Projektdatei oder beim Aufrufen des Compilers (finden Sie unter `--warnon` unter [Compileroptionen](../compiler-options.md)).

## <a name="why-immutable"></a>Warum unveränderlich?

Unveränderliche Werte sind Werte, die im Verlauf der Ausführung des Programms nicht geändert werden können. Wenn Sie an Sprachen wie C++, Visual Basic oder C# gewöhnt sind, finden Sie es möglicherweise überraschend, dass F# unveränderlichen Werte Vorrang gewährt, anstelle von Variablen, denen während der Ausführung eines Programms neue Werte zugeordnet werden können. Unveränderliche Daten sind ein wichtiges Element der funktionalen Programmierung. In einer Multithreadumgebung sind freigegebene änderbare Variablen, die von vielen unterschiedlichen Threads geändert werden können, schwierig zu verwalten. Darüber hinaus kann man mit änderbaren Variablen manchmal nur schwer feststellen, ob eine Variable geändert werden kann, wenn sie an eine andere Funktion übergeben wird.

In reinen funktionalen Sprachen gibt es keine Variablen, und Funktionen verhalten sich genau wie mathematische Funktionen. Wo Code in einer prozeduralen Sprache eine Zuweisung einer Variable verwendet, um einen Wert zu ändern, verfügt der entsprechende Code in einer funktionalen Sprache über einen unveränderlichen Wert, der die Eingabe ist, eine unveränderliche Funktion und über verschiedene unveränderliche Werte als Ausgabe. Diese mathematische Strenge ermöglicht genauere Schlussfolgerungen über das Verhalten des Programms. Diese Strenge ist der Grund dafür, dass Compiler Code präziser überprüfen und effizienter optimieren können, und es erleichtert Entwicklern das Verstehen und korrekte Schreiben von Code. Funktionaler Code ist daher häufig einfacher zu debuggen als gewöhnlicher prozeduraler Code.

F# ist keine rein funktionale Programmiersprache, aber unterstützt funktionale Programmierung umfassend. Die Verwendung von unveränderlichen Werten wird empfohlen, da Ihr Code dadurch von einem wichtigen Aspekt der funktionalen Programmierung profitieren kann.

## <a name="mutable-variables"></a>Änderbare Variablen

Sie können mithilfe des Schlüsselworts `mutable` eine Variable angeben, die geändert werden kann. Änderbare Variablen in F# sollten grundsätzlich einen begrenzten Bereich haben, entweder als Feld eines Typs oder als lokaler Wert. Änderbare Variablen mit einem begrenzten Gültigkeitsbereich sind einfacher zu steuern und werden seltener auf falsche Weise geändert.

Sie können einen Anfangswert für eine änderbare Variable zuweisen, indem Sie das `let`-Schlüsselwort auf die gleiche Weise verwenden, wie Sie einen Wert definieren würden. Der Unterschied ist jedoch, dass Sie anschließend den änderbaren Variablen neue Werte zuweisen können, indem Sie den `<-`-Operator verwenden, wie im folgenden Beispiel.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet602.fs)]

Werte, die markiert `mutable` automatisch auf heraufgestuft werden `'a ref` Wenn durch eine Closure erfasst, einschließlich Formularen, die z. B. Erstellen von Abschlüssen, `seq` Generatoren. Wenn Sie in diesem Fall benachrichtigt werden möchten, aktivieren Sie die Warnung 3180 in der Projektdatei oder beim Aufrufen des Compilers.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----|-----------|
|[let-Bindungen](../functions/let-bindings.md)|Enthält Informationen zur Verwendung der `let` Schlüsselwort, um die Bindung von Namen an Werte und Funktionen.|
|[Funktionen](../functions/index.md)|Bietet eine Übersicht über Funktionen in F#.|

## <a name="see-also"></a>Siehe auch

- [NULL-Werte](null-Values.md)
- [F#-Sprachreferenz](../index.md)