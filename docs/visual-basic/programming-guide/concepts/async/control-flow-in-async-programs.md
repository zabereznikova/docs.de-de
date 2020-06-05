---
title: Ablaufsteuerung in asynchronen Programmen
ms.date: 07/20/2015
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
ms.openlocfilehash: 0c479b9dd2a691b1b353fac54ee3320a895b1c7f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396661"
---
# <a name="control-flow-in-async-programs-visual-basic"></a>Ablaufsteuerung in asynchronen Programmen (Visual Basic)

Sie können asynchrone Programme mithilfe der Schlüsselwörter `Async` und `Await` einfacher schreiben und verwalten. Möglicherweise könnten Sie jedoch die Ergebnisse überraschen, wenn Sie die Funktionsweise Ihres Programms nicht verstehen. In diesem Thema wird die Ablaufsteuerung durch ein einfaches asynchrones Programm nachvollzogen, um darzustellen, wann die Steuerung von einer Methode zu einer anderen springt und welche Informationen jedes Mal übertragen werden.

> [!NOTE]
> Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt.

Im allgemeinen markieren Sie Methoden, die asynchronen Code enthalten, mit dem [Async](../../../language-reference/modifiers/async.md) -Modifizierer. In einer Methode, die mit einem Async-Modifizierer markiert ist, können Sie einen Wait [(Visual Basic)](../../../language-reference/operators/await-operator.md) -Operator verwenden, um anzugeben, wo die Methode angehalten wird, um auf den Abschluss eines aufgerufenen asynchronen Prozesses zu warten. Weitere Informationen finden Sie unter [asynchrone Programmierung mit Async und warten (Visual Basic)](index.md).

Im folgenden Beispiel werden asynchrone Methoden verwendet, um den Inhalt einer angegebenen Website als Zeichenfolge herunterzuladen und um die Länge der Zeichenfolge anzuzeigen. Das Beispiel enthält die folgenden beiden Methoden.

- `startButton_Click`, die `AccessTheWebAsync` aufruft und das Ergebnis angezeigt.

- `AccessTheWebAsync`, die den Inhalt einer Website als Zeichenfolge herunterlädt und die Länge der Zeichenfolge zurückgibt. `AccessTheWebAsync` verwendet eine asynchrone <xref:System.Net.Http.HttpClient>-Methode, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, um den Inhalt herunterzuladen.

Nummerierte Ausgabezeilen werden über das Programm verteilt an strategischen Stellen angezeigt, die dabei helfen sollen, die Ausführung des Programms nachzuvollziehen und zu verdeutlichen, was an den markierten Punkten geschieht. Die Ausgabezeilen werden durchgehend von "ONE" (Eins) bis "SIX" (Sechs) bezeichnet. Die Bezeichnungen entsprechen der Reihenfolge, in der das Programm diese Codezeilen erreicht.

Im folgenden Code wird die Gliederung des Programms angezeigt.

```vb
Class MainWindow

    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click

        ' ONE
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()

        ' FOUR
        Dim contentLength As Integer = Await getLengthTask

        ' SIX
        ResultsTextBox.Text &=
            vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

    End Sub

    Async Function AccessTheWebAsync() As Task(Of Integer)

        ' TWO
        Dim client As HttpClient = New HttpClient()
        Dim getStringTask As Task(Of String) =
            client.GetStringAsync("https://msdn.microsoft.com")

        ' THREE
        Dim urlContents As String = Await getStringTask

        ' FIVE
        Return urlContents.Length
    End Function

End Class
```

An jeder der mit "ONE" bis "SIX" bezeichneten Stellen werden Informationen über den aktuellen Status des Programms angezeigt. Es wird die folgende Ausgabe generiert:

```console
ONE:   Entering startButton_Click.
           Calling AccessTheWebAsync.

TWO:   Entering AccessTheWebAsync.
           Calling HttpClient.GetStringAsync.

THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.

FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.

FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.

SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.

Length of the downloaded string: 33946.
```

## <a name="set-up-the-program"></a>Das Programm einrichten

Sie können den Code, der in diesem Thema verwendet wird, von MSDN herunterladen oder Sie können ihn selbst erstellen.

> [!NOTE]
> Zum Ausführen des Beispiels müssen Visual Studio 2012 oder höher und die .NET Framework 4,5 oder höher auf dem Computer installiert sein.

### <a name="download-the-program"></a>Das Programm herunterladen

Sie können die Anwendung für dieses Thema von [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) herunterladen. Mithilfe der folgenden Schritte wird das Programm geöffnet und ausgeführt.

1. Entzippen Sie die heruntergeladene Datei und starten Sie anschließend Visual Studio.

2. Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.

3. Navigieren Sie zu dem Ordner, der den entzippten Beispielcode enthält, öffnen Sie die Projektmappendatei (SLN) und drücken Sie dann die F5-TASTE, um das Projekt zu erstellen und auszuführen.

### <a name="build-the-program-yourself"></a>Das Programm selbst erstellen

Das folgende Windows Presentation Foundation (WPF)-Projekt enthält das Codebeispiel für dieses Thema.

Um das Projekt auszuführen, führen Sie die folgenden Schritte aus:

1. Starten Sie Visual Studio.

2. Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.

    Das Dialogfeld **Neues Projekt** wird angezeigt.

3. Wählen Sie im Bereich **installierte Vorlagen** die Option **Visual Basic**aus, und wählen Sie dann in der Liste der Projekttypen die Option **WPF-Anwendung** aus.

4. Geben Sie `AsyncTracer` als Name für das Projekt ein, und wählen Sie dann die Schaltfläche **OK** aus.

    Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.

5. Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.

    Wenn die Registerkarte nicht sichtbar ist, öffnen Sie das Kontextmenü für „MainWindow.xaml“ im **Projektmappen-Explorer**, und wählen Sie dann **Code anzeigen**aus.

6. Ersetzen Sie den automatisch generierten Code in der **XAML**-Ansicht der Datei „MainWindow.xaml“ durch den folgenden Code.

    ```vb
    <Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="MainWindow"
        Title="Control Flow Trace" Height="350" Width="525">
        <Grid>
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="221,10,0,0" VerticalAlignment="Top" Width="75"/>
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="510" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" d:LayoutOverrides="HorizontalMargin"/>

        </Grid>
    </Window>
    ```

    Ein einfaches Fenster, das ein Textfeld und eine Schaltfläche enthält, wird in der **Entwurfsansicht** der Datei „MainWindow.xaml“ angezeigt.

7. Fügen Sie einen Verweis für <xref:System.Net.Http> hinzu.

8. Öffnen Sie in **Projektmappen-Explorer**das Kontextmenü für "MainWindow. XAML. vb", und wählen Sie dann **Code anzeigen**aus.

9. Ersetzen Sie den Code in "MainWindow. XAML. vb" durch den folgenden Code.

    ```vb
    ' Add an Imports statement and a reference for System.Net.Http.
    Imports System.Net.Http

    Class MainWindow

        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click

            ' The display lines in the example lead you through the control shifts.
            ResultsTextBox.Text &= "ONE:   Entering StartButton_Click." & vbCrLf &
                "           Calling AccessTheWebAsync." & vbCrLf

            Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()

            ResultsTextBox.Text &= vbCrLf & "FOUR:  Back in StartButton_Click." & vbCrLf &
                "           Task getLengthTask is started." & vbCrLf &
                "           About to await getLengthTask -- no caller to return to." & vbCrLf

            Dim contentLength As Integer = Await getLengthTask

            ResultsTextBox.Text &= vbCrLf & "SIX:   Back in StartButton_Click." & vbCrLf &
                "           Task getLengthTask is finished." & vbCrLf &
                "           Result from AccessTheWebAsync is stored in contentLength." & vbCrLf &
                "           About to display contentLength and exit." & vbCrLf

            ResultsTextBox.Text &=
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)
        End Sub

        Async Function AccessTheWebAsync() As Task(Of Integer)

            ResultsTextBox.Text &= vbCrLf & "TWO:   Entering AccessTheWebAsync."

            ' Declare an HttpClient object.
            Dim client As HttpClient = New HttpClient()

            ResultsTextBox.Text &= vbCrLf & "           Calling HttpClient.GetStringAsync." & vbCrLf

            ' GetStringAsync returns a Task(Of String).
            Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")

            ResultsTextBox.Text &= vbCrLf & "THREE: Back in AccessTheWebAsync." & vbCrLf &
                "           Task getStringTask is started."

            ' AccessTheWebAsync can continue to work until getStringTask is awaited.

            ResultsTextBox.Text &=
                vbCrLf & "           About to await getStringTask & return a Task(Of Integer) to StartButton_Click." & vbCrLf

            ' Retrieve the website contents when task is complete.
            Dim urlContents As String = Await getStringTask

            ResultsTextBox.Text &= vbCrLf & "FIVE:  Back in AccessTheWebAsync." &
                vbCrLf & "           Task getStringTask is complete." &
                vbCrLf & "           Processing the return statement." &
                vbCrLf & "           Exiting from AccessTheWebAsync." & vbCrLf

            Return urlContents.Length
        End Function

    End Class
    ```

10. Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .

    Die folgende Ausgabe sollte angezeigt werden:

    ```console
    ONE:   Entering startButton_Click.
               Calling AccessTheWebAsync.

    TWO:   Entering AccessTheWebAsync.
               Calling HttpClient.GetStringAsync.

    THREE: Back in AccessTheWebAsync.
               Task getStringTask is started.
               About to await getStringTask & return a Task<int> to startButton_Click.

    FOUR:  Back in startButton_Click.
               Task getLengthTask is started.
               About to await getLengthTask -- no caller to return to.

    FIVE:  Back in AccessTheWebAsync.
               Task getStringTask is complete.
               Processing the return statement.
               Exiting from AccessTheWebAsync.

    SIX:   Back in startButton_Click.
               Task getLengthTask is finished.
               Result from AccessTheWebAsync is stored in contentLength.
               About to display contentLength and exit.

    Length of the downloaded string: 33946.
    ```

## <a name="trace-the-program"></a>Ablaufverfolgung für das Programm durchführen

### <a name="steps-one-and-two"></a>Schritte EINS und ZWEI

Durch die ersten beiden Ausgabezeilen wird der Pfad verfolgt, während `startButton_Click``AccessTheWebAsync` aufruft und `AccessTheWebAsync` die asynchrone <xref:System.Net.Http.HttpClient>-Methode <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> aufruft. Im folgenden Bild werden die Aufrufe von Methode zu Methode gezeigt.

![Schritte EINS und ZWEI](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "Asynctrace-Onetwo")

Der Rückgabetyp sowohl von `AccessTheWebAsync` als auch von `client.GetStringAsync` ist <xref:System.Threading.Tasks.Task%601>. Für `AccessTheWebAsync` ist TResult eine ganze Zahl. Für `GetStringAsync` ist TResult eine Zeichenfolge. Weitere Informationen zu Async-Methoden Rückgabe Typen finden Sie unter asynchrone [Rückgabe Typen (Visual Basic)](async-return-types.md).

Eine asynchrone Methode, die eine Aufgabe zurückgibt, gibt eine Aufgabeninstanz zurück, wenn die Steuerung wieder zum Aufrufer zurückwechselt. Die Steuerung kehrt von einer asynchronen Methode wieder zu deren Aufrufer zurück, wenn entweder ein `Await`-Operator in der aufgerufenen Methode auftritt oder die aufgerufene Methode beendet wird. Durch die durchgehend mit "THREE" (Drei) bis "SIX" (Sechs) bezeichneten Ausgabezeilen wird dieser Teil des Prozesses verfolgt.

### <a name="step-three"></a>Schritt DREI

In `AccessTheWebAsync` wird die asynchrone Methode <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> aufgerufen, um den Inhalt der Zielwebseite herunterzuladen. Die Steuerung kehrt von `client.GetStringAsync` zu `AccessTheWebAsync` zurück, wenn `client.GetStringAsync` zurückgegeben wird.

Die `client.GetStringAsync`-Methode gibt eine Zeichenfolgenaufgabe zurück, die der `getStringTask`-Variablen in `AccessTheWebAsync` zugewiesen wird. Die folgende Zeile im Beispielprogramm zeigt den Aufruf von `client.GetStringAsync` und die Zuweisung.

```vb
Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")
```

Sie können sich die Aufgabe als eine Zusage von `client.GetStringAsync` vorstellen, schließlich eine tatsächliche Zeichenfolge zu erzeugen. In der Zwischenzeit, wenn `AccessTheWebAsync` auszuführende Aufgaben hat, die nicht von der zugesagten Zeichenfolge von `client.GetStringAsync` abhängen, können diese Aufgaben fortgesetzt werden, während `client.GetStringAsync` wartet. Im Beispiel bieten die folgenden, mit „THREE“ bezeichneten Ausgabezeilen die Gelegenheit, um unabhängige Aufgaben auszuführen.

```console
THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.
```

 Durch die folgende Anweisung wird die Ausführung in `AccessTheWebAsync` angehalten, wenn `getStringTask` erwartet wird.

```vb
Dim urlContents As String = Await getStringTask
```

Die folgende Abbildung zeigt die Ablauf Steuerung von `client.GetStringAsync` bis zur Zuweisung zu `getStringTask` und von der Erstellung von `getStringTask` bis zur Anwendung eines Erwartungs Operators.

![Schritt 3](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "Asynctrace: drei")

Durch den await-Ausdruck wird `AccessTheWebAsync` angehalten, bis `client.GetStringAsync` zurückgegeben wird. In der Zwischenzeit kehrt die Steuerung zum Aufrufer von `AccessTheWebAsync`, `startButton_Click`, zurück.

> [!NOTE]
> In der Regel warten Sie sofort auf den Aufruf einer asynchronen Methode. Beispielsweise könnte die folgende Zuweisung den vorherigen Code ersetzen, der `getStringTask` erstellt und anschließend darauf wartet: `Dim urlContents As String = Await client.GetStringAsync("https://msdn.microsoft.com")`
>
> In diesem Thema wird der await-Operator später angewendet, um die Ausgabezeilen anzupassen, die die Ablaufsteuerung durch das Programm markieren.

### <a name="step-four"></a>Schritt VIER

Der deklarierte Rückgabetyp von `AccessTheWebAsync` ist `Task(Of Integer)`. Wenn `AccessTheWebAsync` angehalten wird, wird daher eine Ganzzahlaufgabe an `startButton_Click` zurückgegeben. Sie sollten verstanden haben, dass die zurückgegebene Aufgabe nicht `getStringTask` ist. Die zurückgegebene Aufgabe ist eine neue Ganzzahlaufgabe, die die verbleibenden Aufgaben in der angehaltenen Methode, `AccessTheWebAsync`, darstellt. Die Aufgabe ist eine Zusage von `AccessTheWebAsync`, eine ganze Zahl zu erzeugen, wenn die Aufgabe abgeschlossen wird.

Die folgende Anweisung weist diese Aufgabe der `getLengthTask`-Variablen zu.

```vb
Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()
```

Wie in `AccessTheWebAsync` kann `startButton_Click` mit Aufgaben fortsetzen, die nicht von den Ergebnissen der asynchronen Aufgabe (`getLengthTask`) abhängen, bis diese Aufgabe erwartet wird. Die folgenden Ausgabezeilen stellen die Arbeit dar:

```console
FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.
```

Die Ausführung von `startButton_Click` wird angehalten, wenn `getLengthTask` erwartet wird. Durch die folgende Zuweisungsanweisung wird `startButton_Click` angehalten, bis `AccessTheWebAsync` abgeschlossen ist.

```vb
Dim contentLength As Integer = Await getLengthTask
```

In der folgenden Abbildung veranschaulichen die Pfeile die Ablaufsteuerung vom await-Ausdruck in `AccessTheWebAsync` zur Zuweisung eines Werts an `getLengthTask`, gefolgt von normaler Verarbeitung in `startButton_Click` bis `getLengthTask` erwartet wird.

![Schritt 4](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "Asynctrace-vier")

### <a name="step-five"></a>Schritt FÜNF

Wenn `client.GetStringAsync` signalisiert, dass es abgeschlossen ist, wird die Verarbeitung in `AccessTheWebAsync` aus dem Anhalten freigegeben und kann nach dem await-Ausdruck fortgesetzt werden. Die folgenden Ausgabezeilen stellen die Wiederaufnahme der Verarbeitung dar:

```console
FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.
```

Der Operand der return-Anweisung, `urlContents.Length`, wird in der Aufgabe gespeichert, die `AccessTheWebAsync` zurückgibt. Der await-Ausdruck ruft diesen Wert von `getLengthTask` in `startButton_Click` ab.

Im folgenden Bild wird die Übertragung der Steuerung gezeigt, nachdem `client.GetStringAsync` (und `getStringTask`) abgeschlossen sind.

![Schritt FÜNF](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "Asynctrace-5")

`AccessTheWebAsync` wird bis zum Abschluss ausgeführt und die Steuerung kehrt zu `startButton_Click` zurück, das den Abschluss erwartet.

### <a name="step-six"></a>Schritt SECHS

Wenn `AccessTheWebAsync` signalisiert, dass es abgeschlossen ist, kann die Verarbeitung nach der await-Anweisung in `startButton_Async` fortgesetzt werden. Für das Programm gibt es eigentlich nichts mehr zu tun.

Die folgenden Ausgabezeilen stellen die Wiederaufnahme der Verarbeitung in `startButton_Async` dar:

```console
SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.
```

Der await-Ausdruck ruft von `getLengthTask` den ganzzahligen Wert ab, der der Operand der return-Anweisung in `AccessTheWebAsync` ist. Die folgende Anweisung weist diesen Wert der `contentLength`-Variablen zu.

```vb
Dim contentLength As Integer = Await getLengthTask
```

Im folgenden Bild wird die Rückgabe der Steuerung von `AccessTheWebAsync` an `startButton_Click` gezeigt.

![Schritt SECHS](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "Asynctrace-SIX")

## <a name="see-also"></a>Weitere Informationen

- [Asynchronous Programming with Async and Await (Visual Basic) (Asynchrone Programmierung mit Async und Await (Visual Basic))](index.md)
- [Async Return Types (Visual Basic)](async-return-types.md) (Asynchrone Rückgabetypen (Visual Basic))
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await ( Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Thema mit einem asynchronen Beispiel für die Ablaufsteuerung in asynchronen Programmen (C# und Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)
