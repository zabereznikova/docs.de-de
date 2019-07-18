---
title: Versuchen Sie es... Catch... Finally-Anweisung – Visual Basic
description: Informationen Sie zum Verwenden der Ausnahmebehandlung in Visual Basic Try/Catch/Finally-Anweisungen.
ms.date: 12/07/2018
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement [Visual Basic]
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement [Visual Basic], Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement [Visual Basic]
- When keyword [Visual Basic]
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
ms.custom: seodec18
ms.openlocfilehash: 126f20c86bb47e8002382e069ce6236600394aba
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638769"
---
# <a name="trycatchfinally-statement-visual-basic"></a>Try...Catch...Finally-Anweisung (Visual Basic)

Bietet eine Möglichkeit, einige oder alle möglichen Fehler zu behandeln, die beim Ausführen von Code in einem bestimmten Codeblock auftreten können.

## <a name="syntax"></a>Syntax

```vb
Try
    [ tryStatements ]
    [ Exit Try ]
[ Catch [ exception [ As type ] ] [ When expression ]
    [ catchStatements ]
    [ Exit Try ] ]
[ Catch ... ]
[ Finally
    [ finallyStatements ] ]
End Try
```

## <a name="parts"></a>Teile

|Begriff|Definition|
|---|---|
|`tryStatements`|Dies ist optional. Anweisungen, in denen ein Fehler auftreten kann. Kann eine Verbundanweisung sein.|
|`Catch`|Dies ist optional. Mehrere `Catch` Blöcken zulässig. Wenn eine Ausnahme auftritt, bei der Verarbeitung der `Try` blockieren, von denen jede `Catch` Anweisung wird in der Reihenfolge zu bestimmen, ob es die Ausnahme, wobei behandelt im Text überprüft `exception` , die die Ausnahme, die ausgelöst wurde, darstellt.|
|`exception`|Dies ist optional. Ein beliebiger Variablenname. Der Anfangswert von `exception` ist der Wert des ausgelösten Fehlers. Mit verwendet `Catch` an der Fehler abgefangen. Wenn nicht angegeben, die `Catch` Anweisung fängt jede Ausnahme.|
|`type`|Dies ist optional. Gibt den Typ des Klassenfilters. Wenn der Wert des `exception` entspricht dem Typ gemäß `type` oder eines abgeleiteten Typs, der Bezeichner auf das Ausnahmeobjekt gebunden wird.|
|`When`|Dies ist optional. Ein `Catch` -Anweisung mit einem `When` Klausel fängt Ausnahmen nur dann, wenn `expression` ergibt `True`. Ein `When` Klausel wird nur angewendet, nachdem der Typ der Ausnahme ist, überprüft und `expression` bezieht sich möglicherweise auf den Bezeichner, der die Ausnahme darstellt.|
|`expression`|Dies ist optional. Muss implizit in `Boolean`. Ein Ausdruck, der einen generischen Filter beschreibt. In der Regel verwendet zum Filtern nach Fehlernummer. Mit verwendet `When` Schlüsselwort, um die Angabe der Umstände, unter dem der Fehler abgefangen wird.|
|`catchStatements`|Dies ist optional. Anweisungen, um Fehler zu behandeln, die auftreten, in der zugeordneten `Try` Block. Kann eine Verbundanweisung sein.|
|`Exit Try`|Dies ist optional. Schlüsselwort, das von unterbricht die `Try...Catch...Finally` Struktur. Ausführung fortgesetzt wird, durch den Code direkt nach der `End Try` Anweisung. Die `Finally` -Anweisung wird weiterhin ausgeführt werden. Nicht zulässig `Finally` Blöcke.|
|`Finally`|Dies ist optional. Ein `Finally` Block wird immer ausgeführt, wenn die Ausführung eines beliebigen Teils der `Try...Catch` Anweisung.|
|`finallyStatements`|Dies ist optional. Anweisungen, die ausgeführt werden, nachdem sämtlicher Fehler aufgetreten ist.|
|`End Try`|Beendet die `Try...Catch...Finally` Struktur.|

## <a name="remarks"></a>Hinweise

Wenn Sie erwarten, dass eine bestimmte Ausnahme während einer bestimmten Codeabschnitt auftreten kann, fügen Sie den Code in eine `Try` blockieren, und Verwenden einer `Catch` Block zum Beibehalten der Kontrolle und die Ausnahme zu behandeln, wenn es auftritt.

Ein `Try…Catch` Anweisung besteht aus einem `Try` -Block gefolgt von einer oder mehreren `Catch` Klauseln, die Handler für verschiedene Ausnahmen angeben. Wenn eine Ausnahme ausgelöst wird, eine `Try` blockieren, Visual Basic sieht für den `Catch` Anweisung, die die Ausnahme behandelt. Wenn kein übereinstimmendes `Catch` Anweisung nicht gefunden wird, Visual Basic überprüft die Methode, die die aktuelle Methode, und so weiter oben in der Aufrufliste aufgerufen. Wenn kein `Catch` -Block gefunden wird, Visual Basic zeigt die Meldung zu einer nicht behandelten Ausnahme an den Benutzer an und beendet die Ausführung des Programms.

Sie können mehrere `Catch` -Anweisung in einer `Try…Catch` Anweisung. Wenn Sie die Reihenfolge der vorgehen, die `Catch` Klauseln ist von Bedeutung, da sie in der Reihenfolge untersucht werden. Fangen Sie spezifischere Ausnahmen vor den weniger spezifischen ab.

Die folgenden `Catch` Anweisung Bedingungen sind der am wenigsten spezifischen und fängt alle Ausnahmen, die von Ableiten der <xref:System.Exception> Klasse. Kehren Sie normalerweise mithilfe einer der Variationen wie in den letzten `Catch` -block in der `Try...Catch...Finally` -Struktur verwenden, nachdem alle Sie erwarten, dass bestimmten Ausnahmen abfangen. Ablaufsteuerung erreichen niemals eine `Catch` Block, der entweder der Variationen folgt.

- Die `type` ist `Exception`, z.B.: `Catch ex As Exception`

- Die Anweisung hat keine `exception` Variablen, z.B.: `Catch`

Wenn eine `Try…Catch…Finally` Anweisung in einer anderen geschachtelt ist `Try` Visual Basic-Block überprüft zuerst, jede `Catch` -Anweisung in der innersten `Try` Block. Wenn kein übereinstimmendes `Catch` Anweisung gefunden wird, wird die Suche wird fortgesetzt, um die `Catch` Anweisungen von der äußeren `Try…Catch…Finally` Block.

Lokale Variablen aus einer `Try` Block sind nicht verfügbar in eine `Catch` blockiert werden, da sie separate Blöcke sind. Wenn Sie eine Variable in mehreren Blöcken verwenden möchten, deklarieren Sie die Variable außerhalb der `Try...Catch...Finally` Struktur.

> [!TIP]
> Die `Try…Catch…Finally` -Anweisung ist als IntelliSense-Codeausschnitt verfügbar. Erweitern Sie im Codeausschnitt-Manager, **Codemuster - If, For Each, Try Catch, Eigenschaft usw.**, und klicken Sie dann **Fehlerbehandlung (Ausnahmen)**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).

## <a name="finally-block"></a>Finally-block

Wenn Sie eine oder mehrere Anweisungen, die ausgeführt werden muss verfügen, bevor Sie verlassen die `Try` strukturieren, verwenden Sie eine `Finally` Block. Die Steuerung an die `Finally` zu blockieren, nur verwendet werden, bevor sie übergeben die `Try…Catch` Struktur. Dies gilt auch bei eine Ausnahme an einer beliebigen Stelle innerhalb der `Try` Struktur.

Ein `Finally` -Block ist hilfreich beim Ausführen von Code, ausführen muss, auch wenn eine Ausnahme auftritt. Erhält die Kontrolle der `Finally` Block unabhängig davon, wie der `Try...Catch` block beendet wird.

Der Code in eine `Finally` -Block ausgeführt, auch wenn Ihr Code Auftreten einer `Return` -Anweisung in einer `Try` oder `Catch` Block. Steuerelement übergibt die nicht von einem `Try` oder `Catch` Blockieren der entsprechenden `Finally` -block in den folgenden Fällen:

- Ein [End-Anweisung](end-statement.md) gefunden wird in der `Try` oder `Catch` Block.

- Ein <xref:System.StackOverflowException> wird ausgelöst, der `Try` oder `Catch` Block.

Es ist nicht zulässig, die explizit die Ausführung in übertragen einer `Finally` Block. Übertragen die Ausführung von einem `Finally` Block ist nicht gültig, außer über eine Ausnahme.

Wenn eine `Try` -Anweisung enthält nicht mindestens eine `Catch` -Block muss enthalten eine `Finally` Block.

> [!TIP]
> Wenn Sie keine bestimmte Ausnahmen abgefangen der `Using` Anweisung verhält sich wie ein `Try…Finally` Block und garantiert die Freigabe der Ressourcen, unabhängig davon, wie Sie den Block zu beenden. Dies gilt auch für eine nicht behandelte Ausnahme. Weitere Informationen finden Sie unter [using-Anweisung](using-statement.md).

## <a name="exception-argument"></a>Ausnahme-argument

Die `Catch` Block `exception` Argument ist eine Instanz der <xref:System.Exception> Klasse oder eine abgeleitete Klasse die `Exception` Klasse. Die `Exception` Klasseninstanz entspricht des Fehlers in der `Try` Block.

Die Eigenschaften der `Exception` Objekt Hilfe, um die Ursache und den Speicherort einer Ausnahme anzugeben. Z. B. die <xref:System.Exception.StackTrace%2A> Eigenschaftenlisten die aufgerufenen Methoden, die geführt, auf die Ausnahme, die helfen hat, in dem der Fehler im Code zu finden. <xref:System.Exception.Message%2A> Gibt eine Meldung, die die Ausnahme beschreibt. <xref:System.Exception.HelpLink%2A> Gibt einen Link zu einer zugeordneten Hilfedatei zurück. <xref:System.Exception.InnerException%2A> Gibt die `Exception` Objekt, das der aktuellen Ausnahme ist, oder er hat gibt `Nothing` , wenn keine ursprüngliche `Exception`.

## <a name="considerations-when-using-a-trycatch-statement"></a>Überlegungen zur Verwendung ein Try... Catch-Anweisung

Verwenden einer `Try…Catch` Anweisung nur für das Vorkommen des für ungewöhnliche oder unerwartete Programmereignisse zu signalisieren. Die folgenden: Ursachen

- Abfangen von Ausnahmen zur Laufzeit erstellt Mehraufwand und ist wahrscheinlich langsamer als die Prüfung vor, um Ausnahmen zu vermeiden.

- Wenn eine `Catch` Block wird nicht ordnungsgemäß verarbeitet, die die Ausnahme möglicherweise nicht ordnungsgemäß an Benutzer gemeldet werden.

- Behandlung von Ausnahmen wird ein Programm komplexer.

Sie brauchen nicht immer eine `Try…Catch` Anweisung, um eine Bedingung geprüft, die zu rechnen ist. Das folgende Beispiel überprüft, ob eine Datei vorhanden ist, bevor Sie versuchen, ihn zu öffnen. Dies reduziert die Notwendigkeit, Abfangen einer Ausnahme wird ausgelöst, durch die <xref:System.IO.File.OpenText%2A> Methode.

[!code-vb[VbVbalrStatements#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#94)]

Stellen Sie sicher, Code im `Catch` Blöcke Ausnahmen für Benutzer, ob durch eine Thread-sichere-Protokollierung oder die entsprechenden Nachrichten können ordnungsgemäß gemeldet werden. Andernfalls bleiben Ausnahmen möglicherweise unbekannt.

## <a name="async-methods"></a>Async-Methoden

Wenn Sie eine Methode mit kennzeichnen die [Async](../modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../operators/await-operator.md) Operator in der Methode. Eine Anweisung mit der `Await` -Operator hält die Ausführung der Methode, bis die erwartete Aufgabe abgeschlossen ist. Die Aufgabe stellt derzeit ausgeführte Arbeit dar. Wenn die Aufgaben im Zusammenhang mit der `Await` Operator abgeschlossen ist, Ausführung wird fortgesetzt, in der gleichen Methode. Weitere Informationen finden Sie unter [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).

Eine Aufgabe, die von einer asynchronen Methode zurückgegebene kann in einem fehlerhaften Zustand, beenden, der angibt, dass es aufgrund einer nicht behandelten Ausnahme abgeschlossen wurde. Eine Aufgabe kann auch beenden, in einem abgebrochenen Zustand, sodass eine `OperationCanceledException` ausgelöst wird, aus der Await-Ausdruck. Um entweder Typ der Ausnahme abzufangen, platzieren Sie die `Await` -Ausdruck, der die Aufgabe zugeordnet ist eine `Try` block, und fangen die Ausnahme in der `Catch` Block. Ein Beispiel finden Sie weiter unten in diesem Thema.

Eine Aufgabe kann in einem fehlerhaften Zustand sein, da mehrere Ausnahmen für die Fehler verantwortlich waren. Beispielsweise kann die Aufgabe das Ergebnis eines Aufrufs an <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> sein. Wenn Sie eine solche Aufgabe warten, die abgefangene Ausnahme ist nur eine der Ausnahmen, und Sie können nicht vorhersagen, welche Ausnahme abgefangen wird. Ein Beispiel finden Sie weiter unten in diesem Thema.

Ein `Await` Ausdruck kann nicht innerhalb einer `Catch` Block oder `Finally` Block.

## <a name="iterators"></a>Iterators

Ein Iteratorfunktion oder `Get` Accessor führt eine benutzerdefinierte Iteration durch eine Auflistung. Ein Iterator verwendet eine [Yield](yield-statement.md) Anweisung, um jedes Element der Auflistung zu einem Zeitpunkt zurückzugeben. Sie rufen eine Iteratorfunktion mithilfe einer [für jede... Nächste Anweisung](for-each-next-statement.md).

Ein `Yield` -Anweisung werden in einem `Try` Block. Ein `Try` Block mit einer `Yield` -Anweisung kann verfügen `Catch` blockiert, und lassen eine `Finally` Block. Finden Sie im Abschnitt "versuchen Sie es Blöcke in Visual Basic" [Iteratoren](../../programming-guide/concepts/iterators.md) verdeutlicht.

Ein `Yield` Anweisung kann nicht innerhalb einer `Catch` Block oder ein `Finally` Block.

Wenn die `For Each` -Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, ein `Catch` Block in der Iteratorfunktion wird nicht ausgeführt, aber ein `Finally` Block in der Iteratorfunktion ausgeführt wird. Ein `Catch` -Block in einem Iteratorfunktion erfasst nur die Ausnahmen, die innerhalb der Iteratorfunktion auftreten.

## <a name="partial-trust-situations"></a>Teilweise vertrauenswürdigen Umgebungen

In teilweise vertrauenswürdigen Umgebungen, z. B. eine Anwendung, die auf einer Netzwerkfreigabe gehostet `Try...Catch...Finally` fängt keine Ausnahmen zur Codezugriffssicherheit, die auftreten, bevor die Methode, die den Aufruf enthält aufgerufen wird. Im folgenden Beispiel, wenn Sie es auf einer Serverfreigabe und von dort ausführen wird der Fehler "System.Security.SecurityException: Fehler bei der Anforderung." Weitere Informationen zu Sicherheitsausnahmen führen, finden Sie unter den <xref:System.Security.SecurityException> Klasse.

[!code-vb[VbVbalrStatements#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#85)]

In einer solchen teilweise vertrauenswürdige Situation, muss die `Process.Start` Anweisung in einer separaten `Sub`. Dem ersten Aufruf der `Sub` schlägt fehl. Dies ermöglicht `Try...Catch` abzufangen, bevor Sie die `Sub` , enthält `Process.Start` gestartet wird und die Sicherheitsausnahme erzeugt.

## <a name="examples"></a>Beispiele

### <a name="the-structure-of-trycatchfinally"></a>Die Struktur von Try... Catch... Zum Schluss

Das folgende Beispiel veranschaulicht die Struktur der `Try...Catch...Finally` Anweisung.

[!code-vb[VbVbalrStatements#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#86)]  

### <a name="exception-in-a-method-called-from-a-try-block"></a>Ausnahme in einer Methode, die von einem Try-Block aufgerufen

Im folgenden Beispiel die `CreateException` -Methode löst eine `NullReferenceException`. Der Code, der die Ausnahme generiert befindet sich nicht in einem `Try` Block. Aus diesem Grund die `CreateException` Methode die Ausnahme nicht behandelt. Die `RunSample` Methode die Ausnahme behandeln, da der Aufruf der `CreateException` -Methode wird in eine `Try` Block.

Das Beispiel enthält `Catch` Anweisungen für mehrere Typen von Ausnahmen, sortiert, von der spezifischsten bis die allgemeinste.

[!code-vb[VbVbalrStatements#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#91)]

### <a name="the-catch-when-statement"></a>Die Anweisung abfangen, wenn

Das folgende Beispiel zeigt, wie Sie mit einem `Catch When` Anweisung, um nach einem bedingten Ausdruck zu filtern. Wenn der bedingte Ausdruck ergibt `True`, den Code in die `Catch` -Block ausgeführt.

[!code-vb[VbVbalrStatements#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#92)]

### <a name="nested-try-statements"></a>Geschachtelte Try-Anweisungen

Das folgende Beispiel enthält eine `Try…Catch` in enthaltenen-Anweisung eine `Try` Block. Die innere `Catch` Block löst eine Ausnahme aus, dessen `InnerException` -Eigenschaft auf die ursprüngliche Ausnahme festgelegt. Die äußere `Catch` Block gibt, ihre eigene Ausnahme und der inneren Ausnahme.

[!code-vb[VbVbalrStatements#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#93)]

### <a name="exception-handling-for-async-methods"></a>Für die Ausnahmebehandlung für asynchrone Methoden

Im folgenden Beispiel wird die Ausnahmebehandlung für asynchrone Methoden veranschaulicht. Eine Ausnahme abfangen, die für eine asynchrone Aufgabe, gilt die `Await` Ausdruck ist einer `Try` Sperren des Aufrufers, und die Ausnahme ist aufgetreten, in der `Catch` Block.

Heben Sie die Auskommentierung der Zeile `Throw New Exception` im Beispiel auf, um die Ausnahmebehandlung zu veranschaulichen. Die Ausnahme abgefangen wird, der `Catch` blockieren, der Aufgabe `IsFaulted` -Eigenschaftensatz auf `True`, und der Aufgabe `Exception.InnerException` -Eigenschaftensatz auf die Ausnahme.

Heben Sie die Auskommentierung der Zeile `Throw New OperationCancelledException` auf, um zu veranschaulichen, was beim Abbrechen eines asynchronen Prozesses passiert. Die Ausnahme abgefangen wird, der `Catch` Block und der Aufgabe `IsCanceled` -Eigenschaftensatz auf `True`. Jedoch unter bestimmten Umständen, die nicht für dieses Beispiel gelten `IsFaulted` nastaven NA hodnotu `True` und `IsCanceled` nastaven NA hodnotu `False`.

[!code-vb[csAsyncExceptions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#1)]

### <a name="handling-multiple-exceptions-in-async-methods"></a>Behandeln von mehreren Ausnahmen in Async-Methoden

Das folgende Beispiel veranschaulicht die Behandlung von Ausnahmen in Fällen, in denen mehrere Aufgaben zu mehreren Ausnahmen führen können. Die `Try` -Block ist die `Await` Ausdruck für die Aufgabe, die <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> zurückgegeben. Die Aufgabe abgeschlossen ist, bei der drei, auf die Aufgaben <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> wird angewendet, abgeschlossen sind.

Jede der drei Aufgaben löst eine Ausnahme aus. Die `Catch` -Block iteriert durch die Ausnahmen, die im befinden die `Exception.InnerExceptions` Eigenschaft der Aufgabe, die `Task.WhenAll` zurückgegeben.

[!code-vb[csAsyncExceptions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#3)]

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:System.Exception>
- [Exit-Anweisung](exit-statement.md)
- [On Error-Anweisung](on-error-statement.md)
- [Empfohlene Vorgehensweisen für die Verwendung von Codeausschnitten](/visualstudio/ide/best-practices-for-using-code-snippets)
- [Ausnahmebehandlung](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)
- [Throw-Anweisung](throw-statement.md)
