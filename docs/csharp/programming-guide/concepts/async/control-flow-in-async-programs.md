---
title: Ablaufsteuerung in asynchronen Programmen (C#)
description: Hier erfahren Sie mehr über die Ablaufsteuerung in einem einfachen asynchronen C#-Programm, um zu verstehen, wie asynchrone Programme mithilfe der Schlüsselwörter „async“ und „await“ entwickelt und verwaltet werden.
ms.date: 07/20/2015
ms.assetid: fc92b08b-fe1d-4d07-84ab-5192fafe06bb
ms.openlocfilehash: 3946db958466a9f9914a5fa7b37c0db3a64d4b3d
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925370"
---
# <a name="control-flow-in-async-programs-c"></a>Ablaufsteuerung in asynchronen Programmen (C#)

Sie können asynchrone Programme mithilfe der Schlüsselwörter `async` und `await` einfacher schreiben und verwalten. Möglicherweise könnten Sie jedoch die Ergebnisse überraschen, wenn Sie die Funktionsweise Ihres Programms nicht verstehen. In diesem Thema wird die Ablaufsteuerung durch ein einfaches asynchrones Programm nachvollzogen, um darzustellen, wann die Steuerung von einer Methode zu einer anderen springt und welche Informationen jedes Mal übertragen werden.

Im Allgemeinen markieren Sie Methoden mit asynchronem Code mithilfe des [async (C#)](../../../language-reference/keywords/async.md)-Modifizierers. In einer Methode, die mit einem asynchronen Modifizierer markiert ist, können Sie einen [await (C#)](../../../language-reference/operators/await.md)-Operator verwenden, um anzugeben, wo die Methode anhält, um darauf zu warten, dass ein aufgerufener asynchroner Prozess abgeschlossen wird. Weitere Informationen finden Sie unter [Asynchrone Programmierung mit Async und Await (C#)](./index.md).

Im folgenden Beispiel werden asynchrone Methoden verwendet, um den Inhalt einer angegebenen Website als Zeichenfolge herunterzuladen und um die Länge der Zeichenfolge anzuzeigen. Das Beispiel enthält die folgenden beiden Methoden.

- `startButton_Click`, die `AccessTheWebAsync` aufruft und das Ergebnis angezeigt.

- `AccessTheWebAsync`, die den Inhalt einer Website als Zeichenfolge herunterlädt und die Länge der Zeichenfolge zurückgibt. `AccessTheWebAsync` verwendet eine asynchrone <xref:System.Net.Http.HttpClient>-Methode, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, um den Inhalt herunterzuladen.

Nummerierte Ausgabezeilen werden über das Programm verteilt an strategischen Stellen angezeigt, die dabei helfen sollen, die Ausführung des Programms nachzuvollziehen und zu verdeutlichen, was an den markierten Punkten geschieht. Die Ausgabezeilen werden durchgehend von "ONE" (Eins) bis "SIX" (Sechs) bezeichnet. Die Bezeichnungen entsprechen der Reihenfolge, in der das Programm diese Codezeilen erreicht.

Im folgenden Code wird die Gliederung des Programms angezeigt.

```csharp
public partial class MainWindow : Window
{
    // . . .
    private async void startButton_Click(object sender, RoutedEventArgs e)
    {
        // ONE
        Task<int> getLengthTask = AccessTheWebAsync();

        // FOUR
        int contentLength = await getLengthTask;

        // SIX
        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {contentLength}.\r\n";
    }

    async Task<int> AccessTheWebAsync()
    {
        // TWO
        HttpClient client = new HttpClient();
        Task<string> getStringTask =
            client.GetStringAsync("https://msdn.microsoft.com");

        // THREE
        string urlContents = await getStringTask;

        // FIVE
        return urlContents.Length;
    }
}
```

An jeder der mit "ONE" bis "SIX" bezeichneten Stellen werden Informationen über den aktuellen Status des Programms angezeigt. Es wird die folgende Ausgabe generiert:

```output
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

## <a name="set-up-the-program"></a>Einrichten des Programms

Sie können den Code, der in diesem Thema verwendet wird, von MSDN herunterladen oder Sie können ihn selbst erstellen.

> [!NOTE]
> Um das Beispiel ausführen zu können, muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf Ihrem Computer installiert sein.

### <a name="download-the-program"></a>Herunterladen des Programms

Sie können die Anwendung für dieses Thema von [Asynchrones Beispiel: Ablaufsteuerung in asynchronen Programmen](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) herunterladen. Mithilfe der folgenden Schritte wird das Programm geöffnet und ausgeführt.

1. Entzippen Sie die heruntergeladene Datei und starten Sie anschließend Visual Studio.

2. Wählen Sie auf der Menüleiste **Datei** > **Öffnen** > **Projekt/Projektmappe** aus.

3. Navigieren Sie zu dem Ordner, der den entzippten Beispielcode enthält, öffnen Sie die Projektmappendatei (SLN) und drücken Sie dann die **F5**-TASTE, um das Projekt zu erstellen und auszuführen.

### <a name="create-the-program-yourself"></a>Das Programm selbst erstellen

Das folgende Windows Presentation Foundation (WPF)-Projekt enthält das Codebeispiel für dieses Thema.

Um das Projekt auszuführen, führen Sie die folgenden Schritte aus:

1. Starten Sie Visual Studio.

2. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**.

     Das Dialogfeld **Neues Projekt** wird angezeigt.

3. Wählen Sie die Kategorie **Installiert** > **Visual C#**  > **Windows Desktop** und dann aus der Liste der Projektvorlagen **WPF-App** aus.

4. Geben Sie `AsyncTracer` als Name für das Projekt ein, und wählen Sie dann die Schaltfläche **OK** aus.

     Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.

5. Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.

     Wenn die Registerkarte nicht sichtbar ist, öffnen Sie das Kontextmenü für „MainWindow.xaml“ im **Projektmappen-Explorer**, und wählen Sie dann **Code anzeigen**aus.

6. Ersetzen Sie den automatisch generierten Code in der **XAML**-Ansicht der Datei „MainWindow.xaml“ durch den folgenden Code.

    ```csharp
    <Window
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="AsyncTracer.MainWindow"
            Title="Control Flow Trace" Height="350" Width="592">
        <Grid>
            <Button x:Name="startButton" Content="Start
    " HorizontalAlignment="Left" Margin="250,10,0,0" VerticalAlignment="Top" Width="75" Height="24"  Click="startButton_Click" d:LayoutOverrides="GridBox"/>
            <TextBox x:Name="resultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="576" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" Grid.ColumnSpan="3"/>
        </Grid>
    </Window>
    ```

     Ein einfaches Fenster, das ein Textfeld und eine Schaltfläche enthält, wird in der **Entwurfsansicht** der Datei „MainWindow.xaml“ angezeigt.

7. Fügen Sie einen Verweis für <xref:System.Net.Http> hinzu.

8. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für „MainWindow.xaml.cs“, und wählen Sie dann **Code anzeigen** aus.

9. Ersetzen Sie den Code in „MainWindow.xaml.cs“ durch den folgenden Code.

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using System.Windows;
    using System.Windows.Controls;
    using System.Windows.Data;
    using System.Windows.Documents;
    using System.Windows.Input;
    using System.Windows.Media;
    using System.Windows.Media.Imaging;
    using System.Windows.Navigation;
    using System.Windows.Shapes;

    // Add a using directive and a reference for System.Net.Http;
    using System.Net.Http;

    namespace AsyncTracer
    {
        public partial class MainWindow : Window
        {
            public MainWindow()
            {
                InitializeComponent();
            }

            private async void startButton_Click(object sender, RoutedEventArgs e)
            {
                // The display lines in the example lead you through the control shifts.
                resultsTextBox.Text += "ONE:   Entering startButton_Click.\r\n" +
                    "           Calling AccessTheWebAsync.\r\n";

                Task<int> getLengthTask = AccessTheWebAsync();

                resultsTextBox.Text += "\r\nFOUR:  Back in startButton_Click.\r\n" +
                    "           Task getLengthTask is started.\r\n" +
                    "           About to await getLengthTask -- no caller to return to.\r\n";

                int contentLength = await getLengthTask;

                resultsTextBox.Text += "\r\nSIX:   Back in startButton_Click.\r\n" +
                    "           Task getLengthTask is finished.\r\n" +
                    "           Result from AccessTheWebAsync is stored in contentLength.\r\n" +
                    "           About to display contentLength and exit.\r\n";

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }

            async Task<int> AccessTheWebAsync()
            {
                resultsTextBox.Text += "\r\nTWO:   Entering AccessTheWebAsync.";

                // Declare an HttpClient object.
                HttpClient client = new HttpClient();

                resultsTextBox.Text += "\r\n           Calling HttpClient.GetStringAsync.\r\n";

                // GetStringAsync returns a Task<string>.
                Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");

                resultsTextBox.Text += "\r\nTHREE: Back in AccessTheWebAsync.\r\n" +
                    "           Task getStringTask is started.";

                // AccessTheWebAsync can continue to work until getStringTask is awaited.

                resultsTextBox.Text +=
                    "\r\n           About to await getStringTask and return a Task<int> to startButton_Click.\r\n";

                // Retrieve the website contents when task is complete.
                string urlContents = await getStringTask;

                resultsTextBox.Text += "\r\nFIVE:  Back in AccessTheWebAsync." +
                    "\r\n           Task getStringTask is complete." +
                    "\r\n           Processing the return statement." +
                    "\r\n           Exiting from AccessTheWebAsync.\r\n";

                return urlContents.Length;
            }
        }
    }
    ```

10. Drücken Sie die Taste **F5**, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Start**.

    Die folgende Ausgabe wird angezeigt:

    ```output
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

![Schritte EINS und ZWEI](./media/asynctrace-onetwo.png "AsyncTrace-ONETWO")

Der Rückgabetyp sowohl von `AccessTheWebAsync` als auch von `client.GetStringAsync` ist <xref:System.Threading.Tasks.Task%601>. Für `AccessTheWebAsync` ist TResult eine ganze Zahl. Für `GetStringAsync` ist TResult eine Zeichenfolge. Weitere Informationen über Rückgabetypen asynchroner Methoden finden Sie unter [Async Return Types (C#) (Async-Rückgabetypen (C#))](./async-return-types.md).

Eine asynchrone Methode, die eine Aufgabe zurückgibt, gibt eine Aufgabeninstanz zurück, wenn die Steuerung wieder zum Aufrufer zurückwechselt. Die Steuerung kehrt von einer asynchronen Methode wieder zu deren Aufrufer zurück, wenn entweder ein `await`-Operator in der aufgerufenen Methode auftritt oder die aufgerufene Methode beendet wird. Durch die durchgehend mit "THREE" (Drei) bis "SIX" (Sechs) bezeichneten Ausgabezeilen wird dieser Teil des Prozesses verfolgt.

### <a name="step-three"></a>Schritt DREI

In `AccessTheWebAsync` wird die asynchrone Methode <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> aufgerufen, um den Inhalt der Zielwebseite herunterzuladen. Die Steuerung kehrt von `client.GetStringAsync` zu `AccessTheWebAsync` zurück, wenn `client.GetStringAsync` zurückgegeben wird.

 Die `client.GetStringAsync`-Methode gibt eine Zeichenfolgenaufgabe zurück, die der `getStringTask`-Variablen in `AccessTheWebAsync` zugewiesen wird. Die folgende Zeile im Beispielprogramm zeigt den Aufruf von `client.GetStringAsync` und die Zuweisung.

```csharp
Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");
```

 Sie können sich die Aufgabe als eine Zusage von `client.GetStringAsync` vorstellen, schließlich eine tatsächliche Zeichenfolge zu erzeugen. In der Zwischenzeit, wenn `AccessTheWebAsync` auszuführende Aufgaben hat, die nicht von der zugesagten Zeichenfolge von `client.GetStringAsync` abhängen, können diese Aufgaben fortgesetzt werden, während `client.GetStringAsync` wartet. Im Beispiel bieten die folgenden, mit „THREE“ bezeichneten Ausgabezeilen die Gelegenheit, um unabhängige Aufgaben auszuführen.

```output
THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.
```

 Durch die folgende Anweisung wird die Ausführung in `AccessTheWebAsync` angehalten, wenn `getStringTask` erwartet wird.

```csharp
string urlContents = await getStringTask;
```

 Das folgende Bild zeigt die Ablaufsteuerung von `client.GetStringAsync` bis zur Zuweisung von `getStringTask` und von der Erstellung von `getStringTask` bis zur Anwendung eines await-Operators an.

 ![Schritt DREI](./media/asynctrace-three.png "AsyncTrace-Three")

 Durch den await-Ausdruck wird `AccessTheWebAsync` angehalten, bis `client.GetStringAsync` zurückgegeben wird. In der Zwischenzeit kehrt die Steuerung zum Aufrufer von `AccessTheWebAsync`, `startButton_Click`, zurück.

> [!NOTE]
> In der Regel warten Sie sofort auf den Aufruf einer asynchronen Methode. Beispielsweise könnte die folgende Zuweisung den vorherigen Code ersetzen, der `getStringTask` erstellt und anschließend darauf wartet: `string urlContents = await client.GetStringAsync("https://msdn.microsoft.com");`
>
> In diesem Thema wird der await-Operator später angewendet, um die Ausgabezeilen anzupassen, die die Ablaufsteuerung durch das Programm markieren.

### <a name="step-four"></a>Schritt VIER

Der deklarierte Rückgabetyp von `AccessTheWebAsync` ist `Task<int>`. Wenn `AccessTheWebAsync` angehalten wird, wird daher eine Ganzzahlaufgabe an `startButton_Click` zurückgegeben. Sie sollten verstanden haben, dass die zurückgegebene Aufgabe nicht `getStringTask` ist. Die zurückgegebene Aufgabe ist eine neue Ganzzahlaufgabe, die die verbleibenden Aufgaben in der angehaltenen Methode, `AccessTheWebAsync`, darstellt. Die Aufgabe ist eine Zusage von `AccessTheWebAsync`, eine ganze Zahl zu erzeugen, wenn die Aufgabe abgeschlossen wird.

Die folgende Anweisung weist diese Aufgabe der `getLengthTask`-Variablen zu.

```csharp
Task<int> getLengthTask = AccessTheWebAsync();
```

 Wie in `AccessTheWebAsync` kann `startButton_Click` mit Aufgaben fortsetzen, die nicht von den Ergebnissen der asynchronen Aufgabe (`getLengthTask`) abhängen, bis diese Aufgabe erwartet wird. Die folgenden Ausgabezeilen stellen diese Aufgaben dar.

```output
FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.
```

 Die Ausführung von `startButton_Click` wird angehalten, wenn `getLengthTask` erwartet wird. Durch die folgende Zuweisungsanweisung wird `startButton_Click` angehalten, bis `AccessTheWebAsync` abgeschlossen ist.

```csharp
int contentLength = await getLengthTask;
```

 In der folgenden Abbildung veranschaulichen die Pfeile die Ablaufsteuerung vom await-Ausdruck in `AccessTheWebAsync` zur Zuweisung eines Werts an `getLengthTask`, gefolgt von normaler Verarbeitung in `startButton_Click` bis `getLengthTask` erwartet wird.

 ![Schritt VIER](./media/asynctrace-four.png "AsyncTrace-FOUR")

### <a name="step-five"></a>Schritt FÜNF

Wenn `client.GetStringAsync` signalisiert, dass es abgeschlossen ist, wird die Verarbeitung in `AccessTheWebAsync` aus dem Anhalten freigegeben und kann nach dem await-Ausdruck fortgesetzt werden. Die folgenden Ausgabezeilen stellen die Wiederaufnahme der Verarbeitung dar.

```output
FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.
```

 Der Operand der return-Anweisung, `urlContents.Length`, wird in der Aufgabe gespeichert, die `AccessTheWebAsync` zurückgibt. Der await-Ausdruck ruft diesen Wert von `getLengthTask` in `startButton_Click` ab.

 Im folgenden Bild wird die Übertragung der Steuerung gezeigt, nachdem `client.GetStringAsync` (und `getStringTask`) abgeschlossen sind.

 ![Schritt FÜNF](./media/asynctrace-five.png "AsyncTrace-FIVE")

 `AccessTheWebAsync` wird bis zum Abschluss ausgeführt und die Steuerung kehrt zu `startButton_Click` zurück, das den Abschluss erwartet.

### <a name="step-six"></a>Schritt SECHS

Wenn `AccessTheWebAsync` signalisiert, dass es abgeschlossen ist, kann die Verarbeitung nach der await-Anweisung in `startButton_Async` fortgesetzt werden. Für das Programm gibt es eigentlich nichts mehr zu tun.

Die folgenden Ausgabezeilen stellen die Wiederaufnahme der Verarbeitung in `startButton_Async` dar:

```output
SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.
```

 Der await-Ausdruck ruft von `getLengthTask` den ganzzahligen Wert ab, der der Operand der return-Anweisung in `AccessTheWebAsync` ist. Die folgende Anweisung weist diesen Wert der `contentLength`-Variablen zu.

```csharp
int contentLength = await getLengthTask;
```

 Im folgenden Bild wird die Rückgabe der Steuerung von `AccessTheWebAsync` an `startButton_Click` gezeigt.

 ![Schritt SECHS](./media/asynctrace-six.png "AsyncTrace-SIX")

## <a name="see-also"></a>Siehe auch

- [Asynchrone Programmierung mit „async“ und „await“ (C#)](./index.md)
- [Asynchrone Rückgabetypen (C#)](./async-return-types.md)
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Async Sample: Ablaufsteuerung in asynchronen Programmen (C# und Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)
