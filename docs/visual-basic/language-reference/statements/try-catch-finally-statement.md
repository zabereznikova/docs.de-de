---
title: Try... Catch... Abschließend-Anweisung
description: Erfahren Sie, wie Sie die Ausnahmebehandlung mit Visual Basic try/catch/letzenanweisungen verwenden.
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
ms.openlocfilehash: 22f1611786a3da512632b5b547b7ef141c8f65c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391767"
---
# <a name="trycatchfinally-statement-visual-basic"></a>Try...Catch...Finally-Anweisung (Visual Basic)

Bietet eine Möglichkeit, einige oder alle möglichen Fehler zu behandeln, die in einem bestimmten Codeblock auftreten können, während Code weiterhin ausgeführt wird.

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

## <a name="parts"></a>Bestandteile

|Begriff|Definition|
|---|---|
|`tryStatements`|Dies ist optional. Anweisung (en), in der ein Fehler auftreten kann. Kann eine Verbundanweisung sein.|
|`Catch`|Optional. Mehrere `Catch` Blöcke sind zulässig. Wenn bei der Verarbeitung des-Blocks eine Ausnahme auftritt `Try` , wird jede- `Catch` Anweisung in der Text Reihenfolge untersucht, um zu bestimmen, ob die Ausnahme behandelt wird, wobei `exception` die ausgelöste Ausnahme darstellt.|
|`exception`|Optional. Ein beliebiger Variablenname. Der Anfangswert von `exception` ist der Wert des ausgelösten Fehlers. Wird mit verwendet `Catch` , um den aufgefangenen Fehler anzugeben. Wenn Sie nicht vorhanden ist, fängt die- `Catch` Anweisung jede Ausnahme ab.|
|`type`|Optional. Gibt den Typ des Klassen Filters an. Wenn der Wert von vom `exception` Typ ist, der von `type` oder einem abgeleiteten Typ angegeben wird, wird der Bezeichner an das Ausnahme Objekt gebunden.|
|`When`|Optional. Eine- `Catch` Anweisung mit einer- `When` Klausel fängt Ausnahmen nur ab, wenn als `expression` ausgewertet wird `True` . Eine `When` -Klausel wird erst angewendet, nachdem der Typ der Ausnahme überprüft wurde, und `expression` verweist möglicherweise auf den Bezeichner, der die Ausnahme darstellt.|
|`expression`|Optional. Muss implizit in konvertierbar sein `Boolean` . Jeder Ausdruck, der einen generischen Filter beschreibt. Wird normalerweise verwendet, um nach Fehlernummer zu filtern. Wird mit `When` dem-Schlüsselwort verwendet, um Umstände anzugeben, unter denen der Fehler abgefangen wird.|
|`catchStatements`|Optional. Anweisung (en) zum Behandeln von Fehlern, die im zugeordneten- `Try` Block auftreten. Kann eine Verbundanweisung sein.|
|`Exit Try`|Optional. Ein Schlüsselwort, das die `Try...Catch...Finally` Struktur unterbricht. Die Ausführung wird mit dem Code direkt nach der-Anweisung fortgesetzt `End Try` . Die- `Finally` Anweisung wird weiterhin ausgeführt. In-Blöcken nicht zulässig `Finally` .|
|`Finally`|Optional. Ein- `Finally` Block wird immer ausgeführt, wenn die Ausführung einen beliebigen Teil der `Try...Catch` Anweisung verlässt.|
|`finallyStatements`|Optional. Anweisung (en), die ausgeführt wird, nachdem alle anderen Fehler verarbeitet wurden.|
|`End Try`|Beendet die- `Try...Catch...Finally` Struktur.|

## <a name="remarks"></a>Bemerkungen

Wenn Sie davon ausgehen, dass eine bestimmte Ausnahme während eines bestimmten Code Abschnitts auftreten kann, platzieren Sie den Code in einem `Try` -Block, und verwenden Sie einen- `Catch` Block, um die Steuerung beizubehalten und die Ausnahme zu behandeln, wenn Sie auftritt.

Eine- `Try…Catch` Anweisung besteht aus einem- `Try` Block, gefolgt von einer oder mehreren- `Catch` Klauseln, die Handler für verschiedene Ausnahmen angeben. Wenn eine Ausnahme in einem-Block ausgelöst wird `Try` , sucht Visual Basic nach der `Catch` Anweisung, die die Ausnahme behandelt. Wenn keine übereinstimmende `Catch` Anweisung gefunden wird, überprüft Visual Basic die Methode, die die aktuelle Methode aufgerufen hat, usw. Wenn kein- `Catch` Block gefunden wird, zeigt Visual Basic eine unbehandelte Ausnahme Meldung an den Benutzer an und beendet die Ausführung des Programms.

Sie können mehr als eine `Catch` Anweisung in einer- `Try…Catch` Anweisung verwenden. Wenn Sie dies tun, ist die Reihenfolge der `Catch` Klauseln von Bedeutung, da Sie in der richtigen Reihenfolge untersucht werden. Fangen Sie spezifischere Ausnahmen vor den weniger spezifischen ab.

Die folgenden `Catch` Anweisungs Bedingungen sind der spezifischere und fangen alle Ausnahmen ab, die von der-Klasse abgeleitet werden <xref:System.Exception> . Normalerweise sollten Sie eine dieser Variationen als letzten `Catch` Block in der Struktur verwenden `Try...Catch...Finally` , nachdem Sie alle erwarteten Ausnahmen abgefangen haben. Die Ablauf Steuerung kann niemals einen `Catch` Block erreichen, der einer dieser Variationen folgt.

- Ist z. b. `type` `Exception` :`Catch ex As Exception`

- Die-Anweisung hat keine `exception` Variable, z. b.:`Catch`

Wenn eine- `Try…Catch…Finally` Anweisung in einem anderen Block eingebettet ist `Try` , untersucht Visual Basic zuerst jede `Catch` Anweisung im innersten `Try` Block. Wenn keine übereinstimmende `Catch` Anweisung gefunden wird, geht die Suche mit den `Catch` Anweisungen des äußeren `Try…Catch…Finally` Blocks fort.

Lokale Variablen aus einem- `Try` Block sind in einem-Block nicht verfügbar, `Catch` da es sich um separate Blöcke handelt. Wenn Sie eine Variable in mehr als einem Block verwenden möchten, deklarieren Sie die Variable außerhalb der `Try...Catch...Finally` Struktur.

> [!TIP]
> Die- `Try…Catch…Finally` Anweisung ist als IntelliSense-Code Ausschnitt verfügbar. Erweitern Sie im Code Ausschnitt-Manager **Code Patterns-if, for each, try catch, Property, usw**., und dann **Fehlerbehandlung (Ausnahmen)**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).

## <a name="finally-block"></a>Schließlich blockieren

Wenn Sie über eine oder mehrere-Anweisungen verfügen, die vor dem Beenden der- `Try` Struktur ausgeführt werden müssen, verwenden Sie einen- `Finally` Block. Die Steuerung wird an den Block weitergeleitet, `Finally` kurz bevor Sie aus der `Try…Catch` Struktur übergeht. Dies gilt auch, wenn eine Ausnahme an einer beliebigen Stelle innerhalb der `Try` Struktur auftritt.

Ein- `Finally` Block eignet sich zum Ausführen von Code, der ausgeführt werden muss, auch wenn eine Ausnahme vorliegt. Das Steuerelement wird `Finally` unabhängig davon, wie der Block beendet wird, an den Block übertragen `Try...Catch` .

Der Code in einem- `Finally` Block wird auch dann ausgeführt, wenn der Code eine- `Return` Anweisung in einem- `Try` oder-Block findet `Catch` . Das-Steuerelement wird `Try` in den folgenden Fällen nicht von einem-oder- `Catch` Block an den entsprechenden- `Finally` Block übergeben:

- Eine [End-Anweisung](end-statement.md) ist im- `Try` oder- `Catch` Block aufgetreten.

- Eine <xref:System.StackOverflowException> wird im- `Try` oder- `Catch` Block ausgelöst.

Die explizite Übertragung der Ausführung in einen-Block ist ungültig `Finally` . Das übertragen der Ausführung aus einem `Finally` Block ist ungültig, außer durch eine Ausnahme.

Wenn eine `Try` Anweisung nicht mindestens einen `Catch` Block enthält, muss Sie einen-Block enthalten `Finally` .

> [!TIP]
> Wenn Sie keine bestimmten Ausnahmen abfangen müssen, verhält sich die `Using` -Anweisung wie ein `Try…Finally` -Block, und garantiert die Freigabe der Ressourcen, unabhängig davon, wie Sie den Block beenden. Dies gilt auch bei einer nicht behandelten Ausnahme. Weitere Informationen finden Sie unter [using-Anweisung](using-statement.md).

## <a name="exception-argument"></a>Exception-Argument

Das `Catch` Block `exception` Argument ist eine Instanz der- <xref:System.Exception> Klasse oder eine Klasse, die von der-Klasse abgeleitet wird `Exception` . Die- `Exception` Klasseninstanz entspricht dem Fehler, der im- `Try` Block aufgetreten ist.

Die Eigenschaften des- `Exception` Objekts helfen dabei, die Ursache und den Speicherort einer Ausnahme zu ermitteln. Beispielsweise werden in der- <xref:System.Exception.StackTrace%2A> Eigenschaft die aufgerufenen Methoden aufgelistet, die zur Ausnahme geführt haben. Dadurch können Sie ermitteln, wo der Fehler im Code aufgetreten ist. <xref:System.Exception.Message%2A>gibt eine Meldung zurück, in der die Ausnahme beschrieben wird. <xref:System.Exception.HelpLink%2A>Gibt einen Link zu einer zugeordneten Hilfedatei zurück. <xref:System.Exception.InnerException%2A>Gibt das- `Exception` Objekt zurück, das die aktuelle Ausnahme verursacht hat, oder gibt zurück, `Nothing` Wenn kein ursprüngliches vorhanden ist `Exception` .

## <a name="considerations-when-using-a-trycatch-statement"></a>Überlegungen bei der Verwendung von Try... Catch-Anweisung

Verwenden Sie eine- `Try…Catch` Anweisung, um das Vorkommen von ungewöhnlichen oder unerwarteten Programm Ereignissen zu signalisieren. Hierfür sind die folgenden Gründe zu berücksichtigen:

- Das Abfangen von Ausnahmen zur Laufzeit sorgt für zusätzlichen mehr Aufwand und ist wahrscheinlich langsamer als die vorab Überprüfung, um Ausnahmen zu vermeiden.

- Wenn ein `Catch` Block nicht ordnungsgemäß behandelt wird, wird die Ausnahme möglicherweise nicht ordnungsgemäß für die Benutzer gemeldet.

- Durch die Ausnahmebehandlung wird ein Programm komplexer.

Sie benötigen nicht immer eine- `Try…Catch` Anweisung, um eine Bedingung zu prüfen, die wahrscheinlich auftritt. Im folgenden Beispiel wird überprüft, ob eine Datei vorhanden ist, bevor versucht wird, Sie zu öffnen. Dies verringert die Notwendigkeit, eine von der-Methode ausgelöste Ausnahme abzufangen <xref:System.IO.File.OpenText%2A> .

[!code-vb[VbVbalrStatements#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#94)]

Stellen Sie sicher, dass Code in `Catch` Blöcken Ausnahmen für Benutzer ordnungsgemäß melden kann, egal ob durch Thread sichere Protokollierung oder entsprechende Nachrichten. Andernfalls können Ausnahmen unbekannt bleiben.

## <a name="async-methods"></a>Asynchrone Methoden

Wenn Sie eine Methode mit dem [Async](../modifiers/async.md) -Modifizierer markieren, können Sie den [Erwartungs Operator in](../operators/await-operator.md) der-Methode verwenden. Eine-Anweisung mit dem-Operator hält die Ausführung der- `Await` Methode an, bis die erwartete Aufgabe abgeschlossen ist. Die Aufgabe stellt derzeit ausgeführte Arbeit dar. Wenn die dem Operator zugeordnete Aufgabe `Await` abgeschlossen ist, wird die Ausführung in derselben Methode fortgesetzt. Weitere Informationen finden Sie unter [Ablauf Steuerung in Async-Programmen](../../programming-guide/concepts/async/control-flow-in-async-programs.md).

Eine Aufgabe, die von einer asynchronen Methode zurückgegeben wird, kann mit einem fehlerhaften Zustand enden, was darauf hinweist, dass Sie aufgrund einer nicht behandelten Ausnahme abgeschlossen wurde. Eine Aufgabe kann auch in einem abgebrochenen Zustand enden, was dazu führt, `OperationCanceledException` dass aus dem Erwartungs Ausdruck ausgelöst wird. Um einen der beiden Ausnahme Typen abzufangen, platzieren Sie den Ausdruck, der `Await` der Aufgabe zugeordnet ist, in einem `Try` -Block, und fangen Sie die Ausnahme im- `Catch` Block ab. Ein Beispiel finden Sie weiter unten in diesem Thema.

Eine Aufgabe kann sich in einem fehlerhaften Zustand befinden, da mehrere Ausnahmen für Ihren Fehler verantwortlich sind. Beispielsweise kann die Aufgabe das Ergebnis eines Aufrufs an <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> sein. Wenn Sie auf eine solche Aufgabe warten, ist die abgefangene Ausnahme nur eine der Ausnahmen, und Sie können nicht vorhersagen, welche Ausnahme abgefangen wird. Ein Beispiel finden Sie weiter unten in diesem Thema.

Ein `Await` Ausdruck darf sich nicht innerhalb eines `Catch` Blocks oder `Finally` Blocks befinden.

## <a name="iterators"></a>Iterators

Eine Iteratorfunktion oder ein- `Get` Accessor führt eine benutzerdefinierte Iterations Funktion für eine Auflistung aus. Ein Iterator verwendet eine [Yield](yield-statement.md) -Anweisung, um jedes Element der Auflistung einzeln zurückzugeben. Sie stellen eine Iteratorfunktion mithilfe eines [for each-... Next-Anweisung](for-each-next-statement.md).

Eine- `Yield` Anweisung kann sich in einem- `Try` Block befinden. Ein `Try` -Block, der eine `Yield` -Anweisung enthält `Catch` , kann-Blöcke aufweisen und kann einen-Block aufweisen `Finally` . Ein Beispiel finden Sie im Abschnitt "try Blocks in Visual Basic" unter [Iteratoren](../../programming-guide/concepts/iterators.md) .

Eine- `Yield` Anweisung darf sich nicht in einem- `Catch` Block oder einem- `Finally` Block befinden.

Wenn der `For Each` Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, wird ein- `Catch` Block in der Iteratorfunktion nicht ausgeführt, aber ein- `Finally` Block in der Iteratorfunktion wird ausgeführt. Ein `Catch` Block in einer Iteratorfunktion fängt nur Ausnahmen ab, die innerhalb der Iteratorfunktion auftreten.

## <a name="partial-trust-situations"></a>Teilweise vertrauenswürdige Situationen

In teilweise vertrauenswürdigen Situationen, z. b. eine Anwendung, die auf einer Netzwerkfreigabe gehostet wird, `Try...Catch...Finally` fängt keine Sicherheits Ausnahmen ab, die auftreten, bevor die Methode, die den Aufruf enthält, aufgerufen wird. Im folgenden Beispiel wird der Fehler "System. Security. SecurityException: Anforderungs Fehler" erzeugt, wenn Sie ihn auf einer Server Freigabe platzieren und dort ausführen. Weitere Informationen zu Sicherheits Ausnahmen finden Sie unter der- <xref:System.Security.SecurityException> Klasse.

[!code-vb[VbVbalrStatements#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#85)]

In solch einer teilweise vertrauenswürdigen Situation müssen Sie die `Process.Start` Anweisung in einen separaten einfügen `Sub` . Der erste Rückruf von `Sub` schlägt fehl. Dies ermöglicht das `Try...Catch` abfangen, bevor das `Sub` enthält, das enthält, `Process.Start` und die Sicherheits Ausnahme wird ausgelöst.

## <a name="examples"></a>Beispiele

### <a name="the-structure-of-trycatchfinally"></a>Die Struktur von Try... Catch... Endlich

Das folgende Beispiel veranschaulicht die Struktur der- `Try...Catch...Finally` Anweisung.

[!code-vb[VbVbalrStatements#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#86)]  

### <a name="exception-in-a-method-called-from-a-try-block"></a>Ausnahme in einer Methode, die von einem try-Block aufgerufen wird.

Im folgenden Beispiel löst die- `CreateException` Methode eine aus `NullReferenceException` . Der Code, der die Ausnahme generiert, befindet sich nicht in einem- `Try` Block. Daher wird die Ausnahme von der- `CreateException` Methode nicht behandelt. Die- `RunSample` Methode behandelt die Ausnahme, da sich der aufzurufende- `CreateException` Methode in einem- `Try` Block befindet.

Das Beispiel enthält `Catch` Anweisungen für verschiedene Typen von Ausnahmen, die von der spezifischsten bis zur allgemeinsten geordnet sind.

[!code-vb[VbVbalrStatements#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#91)]

### <a name="the-catch-when-statement"></a>Die Catch When-Anweisung

Im folgenden Beispiel wird gezeigt, wie eine-Anweisung verwendet wird `Catch When` , um nach einem bedingten Ausdruck zu filtern. Wenn der bedingte Ausdruck ergibt `True` , wird der Code im- `Catch` Block ausgeführt.

[!code-vb[VbVbalrStatements#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#92)]

### <a name="nested-try-statements"></a>T-Anweisungen in der Liste

Das folgende Beispiel enthält eine- `Try…Catch` Anweisung, die in einem-Block enthalten ist `Try` . Der innere- `Catch` Block löst eine Ausnahme aus, bei der die- `InnerException` Eigenschaft auf die ursprüngliche Ausnahme festgelegt ist. Der äußere `Catch` Block meldet seine eigene Ausnahme und die innere Ausnahme.

[!code-vb[VbVbalrStatements#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#93)]

### <a name="exception-handling-for-async-methods"></a>Ausnahmebehandlung für Async-Methoden

Im folgenden Beispiel wird die Ausnahmebehandlung für asynchrone Methoden veranschaulicht. Zum Abfangen einer Ausnahme, die für eine Async-Aufgabe gilt, befindet sich der `Await` Ausdruck in einem `Try` Block des Aufrufers, und die Ausnahme wird im- `Catch` Block abgefangen.

Heben Sie die Auskommentierung der Zeile `Throw New Exception` im Beispiel auf, um die Ausnahmebehandlung zu veranschaulichen. Die Ausnahme wird im- `Catch` Block abgefangen, die-Eigenschaft der Aufgabe `IsFaulted` wird auf festgelegt `True` , und die-Eigenschaft der Aufgabe `Exception.InnerException` wird auf die-Ausnahme festgelegt.

Heben Sie die Auskommentierung der Zeile `Throw New OperationCancelledException` auf, um zu veranschaulichen, was beim Abbrechen eines asynchronen Prozesses passiert. Die Ausnahme wird im `Catch` -Block abgefangen, und die-Eigenschaft der Aufgabe `IsCanceled` wird auf festgelegt `True` . Unter bestimmten Bedingungen, die für dieses Beispiel nicht gelten, `IsFaulted` wird jedoch auf festgelegt, `True` und `IsCanceled` ist auf festgelegt `False` .

[!code-vb[csAsyncExceptions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#1)]

### <a name="handling-multiple-exceptions-in-async-methods"></a>Behandeln mehrerer Ausnahmen in Async-Methoden

Das folgende Beispiel veranschaulicht die Behandlung von Ausnahmen in Fällen, in denen mehrere Aufgaben zu mehreren Ausnahmen führen können. Der- `Try` Block enthält den `Await` Ausdruck für die Aufgabe, die <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> zurückgegeben hat. Die Aufgabe ist fertiggestellt, wenn die drei Aufgaben, auf die <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> angewendet wird, fertiggestellt sind.

Jede der drei Aufgaben löst eine Ausnahme aus. Der- `Catch` Block durchläuft die Ausnahmen, die in der- `Exception.InnerExceptions` Eigenschaft der Aufgabe, die zurückgegeben hat, gefunden werden `Task.WhenAll` .

[!code-vb[csAsyncExceptions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#3)]

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:System.Exception>
- [Exit-Anweisung](exit-statement.md)
- [On Error-Anweisung](on-error-statement.md)
- [Empfohlene Vorgehensweisen für die Verwendung von Codeausschnitten](/visualstudio/ide/best-practices-for-using-code-snippets)
- [Ausnahmebehandlung](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)
- [Throw-Anweisung](throw-statement.md)
