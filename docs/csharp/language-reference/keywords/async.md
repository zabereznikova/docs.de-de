---
title: async – C#-Referenz
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 89133339a75c70e3ac86d627065e78d555bff71d
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507203"
---
# <a name="async-c-reference"></a>async (C#-Referenz)

Mit dem `async`-Modifizierer können Sie angeben, dass eine Methode, ein [Lambdaausdruck](../../programming-guide/statements-expressions-operators/lambda-expressions.md) oder eine [anonyme Methode](../operators/delegate-operator.md) asynchron ist. Wenn Sie diesen Modifizierer auf Methoden oder Ausdrücke anwenden, wird dies als *asynchrone Methode* bezeichnet. Im folgenden Beispiel wird eine asynchrone Methode mit dem Namen `ExampleMethodAsync` definiert:
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  

Wenn Sie mit der asynchronen Programmierung noch nicht vertraut sind oder nicht wissen, wie eine Async-Methode den [`await`-Operator](../operators/await.md) verwendet, um Aufgaben mit potenziell langer Laufzeit auszuführen, ohne den Thread des Aufrufers zu blockieren, können Sie sich die Einführung unter [Asynchrone Programmierung mit „async“ und „await“](../../programming-guide/concepts/async/index.md) durchlesen. Der folgende Code befindet sich in einer asynchronen Methode und ruft die <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>-Methode auf:
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
Eine asynchrone Methode wird bis zum ersten `await`-Ausdruck synchron ausgeführt. Dann wird die Methode angehalten, bis die erwartete Aufgabe abgeschlossen ist. In der Zwischenzeit wird die Steuerung an den Aufrufer der Methode zurückgegeben, wie das Beispiel in nächsten Thema zeigt.  
  
Wenn die Methode, die mit dem `async`-Schlüsselwort geändert wird, keinen `await`-Ausdruck oder keine await-Anweisung enthält, wird die Methode synchron ausgeführt. Mit einer Compilerwarnung werden Sie auf alle asynchronen Methoden hingewiesen, die keine `await`-Anweisungen enthalten, da dies möglicherweise auf einen Fehler hindeutet. Siehe [Compilerwarnung (Stufe 1) CS4014](../compiler-messages/cs4014.md).  
  
 Das `async`-Schlüsselwort ist insofern kontextabhängig, dass es nur dann ein Schlüsselwort ist, wenn mit ihm eine Methode, ein Lambda-Ausdruck oder eine anonyme Methode geändert wird. In allen anderen Kontexten wird es als Bezeichner interpretiert.  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel werden die Struktur und Ablaufsteuerung zwischen einem asynchronen Ereignishandler, `StartButton_Click`, und einer asynchronen Methode, `ExampleMethodAsync`, veranschaulicht. Das Ergebnis der asynchronen Methode ist die Anzahl von Zeichen einer Webseite. Der Code ist für eine Windows Presentation Foundation (WPF)- oder Windows Store-Anwendung geeignet, die Sie in Visual Studio erstellen. Informationen zum Einrichten der Anwendung finden Sie in den Codekommentaren.  

Sie können diesen Code in Visual Studio als Windows Presentation Foundation (WPF)-App oder Windows Store-App ausführen. Sie benötigen ein Schaltflächen-Steuerelement mit dem Namen `StartButton` und ein Textfeldsteuerelement mit dem Namen `ResultsTextBox`. Denken Sie daran, die Namen und den Handler so festzulegen, dass es in etwa wie folgt aussieht:  

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
        Click="StartButton_Click" Name="StartButton"/>  
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
```
  
So führen Sie den Code als WPF-App aus:  

- Fügen Sie diesen Code in die `MainWindow`-Klasse in „MainWindow.xaml.cs“ ein.  
- Fügen Sie einen Verweis auf „System.Net.Http“ hinzu.  
- Fügen Sie eine `using`-Anweisung für „System.Net.Http“ hinzu.  
  
So führen Sie den Code als Windows Store-App aus:  

- Fügen Sie diesen Code in die `MainPage`-Klasse in „MainPage.xaml.cs“ ein.  
- Fügen Sie using-Anweisungen für „System.Net.Http“ und „System.Threading.Tasks“ hinzu.  
  
[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]
  
> [!IMPORTANT]
> Weitere Informationen zu Aufgaben und zum Code, der während des Wartens auf eine Aufgabe ausgeführt wird, finden Sie unter [Asynchrone Programmierung mit Async und Await](../../programming-guide/concepts/async/index.md). Ein vollständiges WPF-Beispiel, das ähnliche Elemente verwendet, finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).  
  
## <a name="return-types"></a>Rückgabetypen  
Eine asynchrone Methode kann folgende Rückgabetypen haben:

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- [void](../builtin-types/void.md). Von den `async void`-Methoden wird außer für Code für Ereignishandler allgemein abgeraten, da aufrufende Funktionen für diese Methoden `await` nicht verwenden können und einen anderen Mechanismus implementieren müssen, um den erfolgreichen Abschluss oder Fehler zu melden.
- Ab C# 7.0: jeder Typ, der über eine zugängliche `GetAwaiter`-Methode verfügt. Der Typ `System.Threading.Tasks.ValueTask<TResult>` ist eine solche Implementierung. Er ist verfügbar, wenn Sie das NuGet-Paket `System.Threading.Tasks.Extensions` hinzufügen.

Mit der asynchronen Methode können keine [in](./in-parameter-modifier.md)-, [ref](./ref.md)- oder [out](./out-parameter-modifier.md)-Parameter deklariert werden, und sie kann auch keinen [Verweisrückgabewert](../../programming-guide/classes-and-structs/ref-returns.md) aufweisen, es können mit ihr jedoch Methoden aufgerufen werden, die solche Parameter aufweisen.  
  
`Task<TResult>` wird als Rückgabetyp einer Async-Methode angegeben, wenn mit der [return](./return.md)-Anweisung der Methode ein Operand vom Typ `TResult` angegeben wird. `Task` wird verwendet, falls kein sinnvoller Wert zurückgegeben wird, wenn die Methode abgeschlossen ist. Das bedeutet, dass ein Aufruf der Methode einen `Task` zurückgibt. Wenn der `Task` aber abgeschlossen ist, wird jeder `await`-Ausdruck, der auf den `Task` wartet, als `void` ausgewertet.  
  
Der Rückgabetyp `void` wird hauptsächlich zum Definieren von Ereignishandlern verwendet, die diesen Rückgabetyp erfordern. Der Aufrufer einer Async-Methode, die `void` zurückgibt, kann auf ihn nicht warten und keine Ausnahmen auffangen, die von der Methode ausgelöst werden.  

Ab C# 7.0 wird ein anderer Typ zurückgegeben, üblicherweise ein Werttyp, der über eine `GetAwaiter`-Methode verfügt, um Speicherzuteilungen in Codeabschnitten zu minimieren, die für die Leistung entscheidend sind.

Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen](../../programming-guide/concepts/async/async-return-types.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [await](../operators/await.md)
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Asynchrone Programmierung mit Async und Await](../../programming-guide/concepts/async/index.md)
