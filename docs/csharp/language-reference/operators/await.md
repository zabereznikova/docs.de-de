---
description: 'Der Operator „await“: C#-Referenz'
title: 'Der Operator „await“: C#-Referenz'
ms.date: 07/13/2020
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
ms.openlocfilehash: 8dc85bfeaab12d17af4a3e045559e268b228f736
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536469"
---
# <a name="await-operator-c-reference"></a>Der Operator „await“ (C#-Referenz)

Der Operator `await` hält die Auswertung der einschließenden [async](../keywords/async.md)-Methode an, bis der asynchrone Vorgang abgeschlossen ist, der durch seinen Operanden dargestellt wird. Sobald der asynchrone Vorgang abgeschlossen ist, gibt der Operator `await` ggf. das Ergebnis des Vorgangs zurück. Wenn der Operator `await` auf den Operanden angewendet wird, der einen bereits abgeschlossenen Vorgang darstellt, wird das Ergebnis des Vorgangs sofort zurückgegeben, ohne dass die einschließende Methode angehalten wird. Der Operator `await` blockiert nicht den Thread, der die Async-Methode auswertet. Wenn der Operator `await` die einschließende asynchrone Methode anhält, wird das Steuerelement an den Aufrufer der Methode zurückgegeben.

Im folgenden Beispiel gibt die Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType> die Instanz `Task<byte[]>` zurück, die einen asynchronen Vorgang darstellt, der ein Bytearray erzeugt, wenn er abgeschlossen wird. Der Operator `await` hält so lange die Methode `DownloadDocsMainPageAsync` an, bis der Vorgang abgeschlossen ist. Wenn `DownloadDocsMainPageAsync` angehalten wird, wird die Steuerung an die Methode `Main` zurückgegeben. Bei dieser handelt es sich um den Aufrufer von `DownloadDocsMainPageAsync`. Die Methode `Main` wird so lange ausgeführt, bis sie das Ergebnis des asynchronen Vorgangs benötigt, der von der Methode `DownloadDocsMainPageAsync` ausgeführt wird. Wenn <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> alle Bytes abruft, wird der Rest der Methode `DownloadDocsMainPageAsync` ausgewertet. Danach wird der Rest der Methode `Main` ausgewertet.

[!code-csharp[await example](snippets/shared/AwaitOperator.cs)]

Im vorangehenden Beispiel wird die [asynchrone `Main`-Methode](../../programming-guide/main-and-command-args/index.md) verwendet. Dies ist ab C# 7.1 möglich. Weitere Informationen finden Sie im Abschnitt [Der Operator „await“ in der Methode „Main“](#await-operator-in-the-main-method).

> [!NOTE]
> Eine Einführung in die asynchrone Programmierung finden Sie unter [Asynchrone Programmierung mit „async“ und „await“](../../programming-guide/concepts/async/index.md). Die asynchrone Programmierung mit `async` und `await` folgt dem [aufgabenbasierten asynchronen Muster](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

Der Operator `await` kann nur in einer Methode, einem [Lambdaausdruck](lambda-expressions.md) oder einer [anonymen Methode](delegate-operator.md) verwendet werden, die von dem Schlüsselwort [async](../keywords/async.md) geändert wird. Innerhalb einer Async-Methode können Sie den Operator `await` nicht im Text einer synchronen Funktion, innerhalb des Blocks einer [Lock-Anweisung](../keywords/lock-statement.md) oder in einem [unsicheren](../keywords/unsafe.md) Kontext verwenden.

Der Operand des Operators `await` gehört normalerweise einem der folgenden .NET-Typen an: <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> oder <xref:System.Threading.Tasks.ValueTask%601>. Allerdings kann es sich bei jedem Awaitable-Ausdruck um den Operanden des Operators `await` handeln. Weitere Informationen finden Sie im Abschnitt [Awaitable-Ausdrücke](~/_csharplang/spec/expressions.md#awaitable-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Der Ausdruck `await t` ist vom Typ `TResult`, wenn der Ausdruck `t` vom Typ <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.ValueTask%601> ist. Wenn der Ausdruck `t` vom Typ <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.ValueTask> ist, ist `await t` vom Typ `void`. In beiden Fällen löst `await t` die Ausnahme erneut aus, wenn `t` eine Ausnahme auslöst. Weitere Informationen zur Bearbeitung von Ausnahmen finden Sie im Abschnitt [Ausnahmen in Async-Methoden](../keywords/try-catch.md#exceptions-in-async-methods) des Artikels [Try-catch-Anweisung](../keywords/try-catch.md).

Die Schlüsselwörter `async` und `await` sind in C# 5 und höher verfügbar.

## <a name="asynchronous-streams-and-disposables"></a>Asynchrone Datenströme und verwerfbare Objekte

Ab C# 8.0 können Sie asynchrone Datenströme und verwerfbare Elemente verwenden.

Sie können die `await foreach`-Anweisung verwenden, um einen asynchronen Datenstrom zu verarbeiten. Weitere Informationen finden Sie im Artikel [`foreach`-Anweisung](../keywords/foreach-in.md) und im Abschnitt [ Asynchrone Datenströme](../../whats-new/csharp-8.md#asynchronous-streams) des Artikels [Neues in C# 8.0](../../whats-new/csharp-8.md).

Sie können die `await using`-Anweisung nutzen, um ein asynchron verwerfbares Objekt zu nutzen, d. h. ein Objekt eines Typs, der eine <xref:System.IAsyncDisposable>-Schnittstelle implementiert. Weitere Informationen erhalten Sie im Abschnitt [Verwenden von asynchron verwerfbar](../../../standard/garbage-collection/implementing-disposeasync.md#using-async-disposable) des Artikels [Implementieren einer DisposeAsync-Methode](../../../standard/garbage-collection/implementing-disposeasync.md).

## <a name="await-operator-in-the-main-method"></a>Der Operator „await“ in der Methode „Main“

Ab C# 7.1 kann die [Methode `Main`](../../programming-guide/main-and-command-args/index.md), die den Einstiegspunkt der Anwendung darstellt, `Task` oder `Task<int>` zurückgeben. Deshalb muss es sich um eine asynchrone Methode handeln, damit Sie den Operator `await` im Text verwenden können. In früheren C#-Versionen können Sie den Wert der Eigenschaft <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> der Instanz <xref:System.Threading.Tasks.Task%601> abrufen, die von der entsprechenden Async-Methode zurückgegeben wird, um sicherzustellen, dass die Methode `Main` darauf wartet, dass ein asynchroner Vorgang abgeschlossen wird. Für asynchrone Vorgänge, für die kein Wert zurückgegeben wird, können Sie die Methode <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> aufrufen. Informationen zum Auswählen der Sprachversion finden Sie unter [Auswählen der C#-Sprachversion](../configure-language-version.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Await-Ausdrücke](~/_csharplang/spec/expressions.md#await-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [async](../keywords/async.md)
- [Aufgabenbasiertes asynchrones Programmiermodell](../../programming-guide/concepts/async/task-asynchronous-programming-model.md)
- [Asynchrone Programmierung](../../async.md)
- [Async ausführlich](../../../standard/async-in-depth.md)
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“](../../programming-guide/concepts/async/index.md)
- [Tutorial: Generieren und Nutzen asynchroner Datenströme mit C# 8.0 und .NET Core 3.0](../../tutorials/generate-consume-asynchronous-stream.md)
