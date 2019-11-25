---
title: 'Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)'
ms.date: 07/20/2015
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
ms.openlocfilehash: 42b09dab26fd514e184163eaf41aff117d3a463f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281785"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a>Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)

Sie können asynchrone Programme mit den Funktionen „Async/Await“ einfacher und intuitiver schreiben. Sie können asynchronen Code schreiben, der wie synchroner Code aussieht und veranlassen, dass der Compiler die komplizierten Rückruffunktionen und Fortsetzungen verarbeitet, die durch den asynchronen Code für gewöhnlich verursacht werden.

Weitere Informationen über die Funktion „Async“ finden Sie unter [Asynchronous Programming with async and await (C#) (Asynchrone Programmierung mit Async und Await (C#))](./index.md).

Diese exemplarische Vorgehensweise beginnt mit einer synchronen WPF-Anwendung (Windows Presentation Foundation), die die Anzahl der Bytes in einer Liste von Websites summiert. In der exemplarischen Vorgehensweise wird die Anwendung dann mithilfe der neuen Funktionen in eine asynchrone Lösung umgewandelt.

Wenn Sie die Anwendungen nicht selbst erstellen möchten, können Sie [Asynchrones Beispiel: Webzugriff – Exemplarische Vorgehensweise (C# und Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) herunterladen.

> [!NOTE]
> Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.

## <a name="create-a-wpf-application"></a>Erstellen einer WPF-Anwendung

1. Starten Sie Visual Studio.

2. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**.

     Das Dialogfeld **Neues Projekt** wird angezeigt.

3. Wählen Sie im Bereich **Installierte Vorlagen** den Eintrag Visual C# aus, und wählen Sie dann in der Liste der Projekttypen **WPF-Anwendung** aus.

4. Geben Sie im Textfeld **Name** `AsyncExampleWPF` ein, und wählen Sie dann die Schaltfläche **OK** aus.

     Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.

## <a name="design-a-simple-wpf-mainwindow"></a>Entwerfen eines einfachen WPF-MainWindows

1. Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.

2. Wenn das Fenster **Toolbox** nicht sichtbar ist, öffnen Sie das Menü **Ansicht**, und wählen Sie dann **Toolbox** aus.

3. Fügen Sie dem Fenster **MainWindow** ein **Button**-Steuerelement und ein **TextBox**-Steuerelement hinzu.

4. Markieren Sie das **TextBox**-Steuerelement, und legen Sie im Fenster **Eigenschaften** die folgenden Werte fest:

    - Legen Sie die Eigenschaft **Name**auf `resultsTextBox` fest.

    - Legen Sie die Eigenschaft **Height** auf „250“ fest.

    - Legen Sie die Eigenschaft **Width** auf „500“ fest.

    - Geben Sie auf der Registerkarte **Text** eine Festbreitenschriftart wie Lucida Console oder Global Monospace an.

5. Markieren Sie das **Button**-Steuerelement, und legen Sie im Fenster **Eigenschaften** die folgenden Werte fest:

    - Legen Sie die Eigenschaft **Name** auf `startButton` fest.

    - Ändern Sie den Wert der Eigenschaft **Content** von **Button** zu **Start**.

6. Positionieren Sie das Textfeld und die Schaltfläche so, dass beide im Fenster **MainWindow** angezeigt werden.

     Weitere Informationen über den WPF-XAML-Designer finden Sie unter [Erstellen einer Benutzeroberfläche mit dem XAML-Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).

## <a name="add-a-reference"></a>Hinzufügen eines Verweises

1. Markieren Sie im **Projektmappen-Explorer** den Namen des Projekts.

2. Wählen Sie in der Menüleiste die Optionen **Projekt** > **Verweis hinzufügen** aus.

     Das Dialogfeld **Verweis-Manager** wird angezeigt.

3. Stellen Sie oben im Dialogfeld sicher, dass Ihr Projekt auf .NET Framework 4.5 oder höher abzielt.

4. Wählen Sie in der Kategorie **Assemblys** die Option **Framework** aus, wenn sie nicht bereits ausgewählt ist.

5. Aktivieren Sie in der Liste der Namen das Kontrollkästchen **System.Net.Http**.

6. Wählen Sie die Schaltfläche **OK** aus, um das Dialogfeld zu schließen.

## <a name="add-necessary-using-directives"></a>Hinzufügen erforderlicher using-Anweisungen

1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für „MainWindow.xaml.cs“, und wählen Sie dann **Code anzeigen** aus.

2. Fügen Sie die folgenden `using`-Anweisungen am Anfang der Codedatei ein, wenn sie noch nicht vorhanden sind.

    ```csharp
    using System.Net.Http;
    using System.Net;
    using System.IO;
    ```

## <a name="create-a-synchronous-app"></a>Erstellen einer synchronen App

1. Doppelklicken Sie im Entwurfsfenster „MainWindow.xaml“ auf die Schaltfläche **Start**, um den `startButton_Click`-Ereignishandler in „MainWindow.xaml.cs“ zu erstellen.

2. Kopieren Sie in „MainWindow.xaml.cs“ den folgenden Code in den Textteil von `startButton_Click`:

    ```csharp
    resultsTextBox.Clear();
    SumPageSizes();
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";
    ```

    Der Code ruft die Methode `SumPageSizes` auf, die die Anwendung steuert und zeigt eine Meldung an, wenn das Steuerelement zu `startButton_Click` zurückgegeben wird.

3. Der Code für die synchrone Lösung enthält die folgenden vier Methoden:

    - `SumPageSizes`. Enthält eine Liste von Webseiten-URLs aus `SetUpURLList` und ruft dann `GetURLContents` und `DisplayResults` auf, um jede URL zu verarbeiten.

    - `SetUpURLList`. Erstellt und gibt eine Liste der Webadressen zurück.

    - `GetURLContents`. Lädt Inhalte jeder Website herunter und gibt die Inhalte als ein Bytearray zurück.

    - `DisplayResults`. Zeigt die Anzahl der Bytes im Bytearray für jede URL an.

    Kopieren Sie die folgenden vier Methoden, und fügen Sie sie dann unter dem `startButton_Click`-Ereignishandler in „MainWindow.xaml.cs“ ein:

    ```csharp
    private void SumPageSizes()
    {
        // Make a list of web addresses.
        List<string> urlList = SetUpURLList();

        var total = 0;
        foreach (var url in urlList)
        {
            // GetURLContents returns the contents of url as a byte array.
            byte[] urlContents = GetURLContents(url);

            DisplayResults(url, urlContents);

            // Update the total.
            total += urlContents.Length;
        }

        // Display the total count for all of the web addresses.
        resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
    }

    private List<string> SetUpURLList()
    {
        var urls = new List<string>
        {
            "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
            "https://msdn.microsoft.com",
            "https://msdn.microsoft.com/library/hh290136.aspx",
            "https://msdn.microsoft.com/library/ee256749.aspx",
            "https://msdn.microsoft.com/library/hh290138.aspx",
            "https://msdn.microsoft.com/library/hh290140.aspx",
            "https://msdn.microsoft.com/library/dd470362.aspx",
            "https://msdn.microsoft.com/library/aa578028.aspx",
            "https://msdn.microsoft.com/library/ms404677.aspx",
            "https://msdn.microsoft.com/library/ff730837.aspx"
        };
        return urls;
    }

    private byte[] GetURLContents(string url)
    {
        // The downloaded resource ends up in the variable named content.
        var content = new MemoryStream();

        // Initialize an HttpWebRequest for the current URL.
        var webReq = (HttpWebRequest)WebRequest.Create(url);

        // Send the request to the Internet resource and wait for
        // the response.
        // Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        using (WebResponse response = webReq.GetResponse())
        {
            // Get the data stream that is associated with the specified URL.
            using (Stream responseStream = response.GetResponseStream())
            {
                // Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content);
            }
        }

        // Return the result as a byte array.
        return content.ToArray();
    }

    private void DisplayResults(string url, byte[] content)
    {
        // Display the length of each website. The string format
        // is designed to be used with a monospaced font, such as
        // Lucida Console or Global Monospace.
        var bytes = content.Length;
        // Strip off the "https://".
        var displayURL = url.Replace("https://", "");
        resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
    }
    ```

## <a name="test-the-synchronous-solution"></a>Testen der synchronen Lösung

Drücken Sie die Taste **F5**, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Start**.

Die Ausgabe sollte der folgenden Liste ähnlich sein:

```text
msdn.microsoft.com/library/windows/apps/br211380.aspx        383832
msdn.microsoft.com                                            33964
msdn.microsoft.com/library/hh290136.aspx               225793
msdn.microsoft.com/library/ee256749.aspx               143577
msdn.microsoft.com/library/hh290138.aspx               237372
msdn.microsoft.com/library/hh290140.aspx               128279
msdn.microsoft.com/library/dd470362.aspx               157649
msdn.microsoft.com/library/aa578028.aspx               204457
msdn.microsoft.com/library/ms404677.aspx               176405
msdn.microsoft.com/library/ff730837.aspx               143474

Total bytes returned:  1834802

Control returned to startButton_Click.
```

Beachten Sie, dass es ein paar Sekunden dauert, bis die Zahlen angezeigt werden. Während dieser Zeit ist der Benutzeroberflächenthread blockiert, während auf das Herunterladen von angeforderten Ressourcen gewartet wird. Daher können Sie das Anzeigefenster weder verschieben, maximieren, minimieren noch schließen, nachdem Sie die Schaltfläche **Start** ausgewählt haben. Diese Bemühungen sind nicht erfolgreich, bis der Bytezähler angezeigt wird. Wenn eine Website nicht antwortet, erhalten Sie keinen Hinweis darüber, welche Site fehlerhaft ist. Es ist sogar schwierig, mit dem Warten aufzuhören und das Programm zu schließen.

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a>Konvertieren von „GetURLContents“ in eine asynchrone Methode

1. Für das Konvertieren der synchronen Projektmappe in eine asynchrone Projektmappe empfiehlt es sich, in `GetURLContents` zu beginnen, da die Aufrufe der <xref:System.Net.HttpWebRequest>-Methode <xref:System.Net.HttpWebRequest.GetResponse%2A> und der <xref:System.IO.Stream>-Methode <xref:System.IO.Stream.CopyTo%2A> dort erfolgen, wo die Anwendung auf das Web zugreift. .NET Framework erleichtert die Konvertierung, indem asynchrone Versionen beider Methoden bereitgestellt werden.

     Weitere Informationen über die in `GetURLContents` verwendeten Methoden finden Sie unter <xref:System.Net.WebRequest>.

    > [!NOTE]
    > Beim Befolgen der Schritte in dieser exemplarischen Vorgehensweise treten verschiedene Compilerfehler auf. Sie können diese ignorieren und mit der exemplarischen Vorgehensweise fortfahren.

     Ändern Sie die Methode, die aufgerufen wird, in der dritten Zeile von `GetURLContents` von `GetResponse` zur asynchronen, aufgabenbasierten <xref:System.Net.WebRequest.GetResponseAsync%2A>-Methode.

    ```csharp
    using (WebResponse response = webReq.GetResponseAsync())
    ```

2. `GetResponseAsync` gibt einen Wert vom Typ <xref:System.Threading.Tasks.Task%601> zurück. In diesem Fall weist die *Aufgabenrückgabevariable*, `TResult`, den Typ <xref:System.Net.WebResponse> auf. Mit dieser Aufgabe soll ein tatsächliches `WebResponse`-Objekt erstellt werden, nachdem die angeforderten Daten heruntergeladen und das Ausführen der Aufgabe abgeschlossen wurde.

     Wenden Sie analog zur Darstellung im folgenden Code zum Abrufen des `WebResponse`-Werts aus der Aufgabe einen [await](../../../language-reference/operators/await.md)-Operator für den Aufruf von `GetResponseAsync` an.

    ```csharp
    using (WebResponse response = await webReq.GetResponseAsync())
    ```

     Der `await`-Operator hält die Ausführung der aktuellen Methode `GetURLContents` an, bis die Aufgabe abgeschlossen ist. In der Zwischenzeit kehrt die Steuerung zum Aufrufer der aktuellen Methode zurück. In diesem Beispiel lautet die aktuelle Methode `GetURLContents`, und der Aufrufer ist `SumPageSizes`. Wenn die Aufgabe abgeschlossen ist, wird das zugesicherte `WebResponse`-Objekt als Wert der erwarteten Aufgabe erstellt und zur Variable `response` zugewiesen.

     Die vorherige Anweisung kann in die folgenden zwei Anweisungen getrennt werden, um zu verdeutlichen, was geschieht.

    ```csharp
    //Task<WebResponse> responseTask = webReq.GetResponseAsync();
    //using (WebResponse response = await responseTask)
    ```

     Durch den Aufruf von `webReq.GetResponseAsync` wird `Task(Of WebResponse)` oder `Task<WebResponse>` zurückgegeben. Anschließend wird ein await-Operator auf die Aufgabe angewendet, um den `WebResponse`-Wert abzurufen.

     Wenn Ihre asynchrone Methode Aktionen vornehmen muss, die nicht von der Fertigstellung der Aufgabe abhängen, kann die Methode diese Aktionen zwischen zwei Anweisungen fortsetzen, und zwar nach dem Aufruf der asynchronen Methode und vor dem Anwenden des `await`-Operators. Beispiele finden Sie unter [How to make multiple web requests in parallel by using async and await (C#) (Vorgehensweise: Gleichzeitiges Erstellen von mehreren Webanforderungen mit „Async“ und „Await“ (C#))](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) und [Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).

3. Da Sie den Operator `await` im vorherigen Schritt hinzugefügt haben, tritt ein Compilerfehler auf. Der Operator kann nur in Methoden verwendet werden, die mit dem Modifizierer [async](../../../language-reference/keywords/async.md) markiert sind. Ignorieren Sie den Fehler, während Sie die Konvertierungsschritte zum Ersetzen des Aufrufs von `CopyTo` mit einem Aufruf von `CopyToAsync` wiederholen.

    - Ändern Sie den Namen der Methode, die für <xref:System.IO.Stream.CopyToAsync%2A> aufgerufen wird.

    - Die Methode `CopyTo` oder `CopyToAsync` kopiert Bytes zu ihrem Argument `content` und gibt keinen sinnvollen Wert zurück. In der synchronen Version ist der Aufruf von `CopyTo` eine einfache Anweisung, die keinen Wert zurückgibt. Die asynchrone Version `CopyToAsync` gibt ein <xref:System.Threading.Tasks.Task> zurück. Die Aufgabe funktioniert wie „Task(void)“ und ermöglicht, dass auf die Methode gewartet wird. Wenden Sie `Await` oder `await` auf den Aufruf von `CopyToAsync` an, wie dies im folgenden Code gezeigt wird.

        ```csharp
        await responseStream.CopyToAsync(content);
        ```

         Die vorherige Anweisung kürzt die folgenden zwei Codezeilen.

        ```csharp
        // CopyToAsync returns a Task, not a Task<T>.
        //Task copyTask = responseStream.CopyToAsync(content);

        // When copyTask is completed, content contains a copy of
        // responseStream.
        //await copyTask;
        ```

4. Somit muss nur noch die Methodensignatur in `GetURLContents` angepasst werden. Der `await`-Operator kann nur in Methoden verwendet werden, die mit dem Modifizierer [async](../../../language-reference/keywords/async.md) markiert sind. Fügen Sie den Modifizierer hinzu, um die Methode als eine *async*-Methode zu markieren, wie im folgenden Code gezeigt wird.

    ```csharp
    private async byte[] GetURLContents(string url)
    ```

5. Der Rückgabetyp einer Async-Methode kann nur <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> oder `void` in C# sein. Für gewöhnlich wird ein Rückgabetyp `void` nur in einem asynchronen Ereignishandler verwendet, bei dem `void` erforderlich ist. In anderen Fällen verwenden Sie `Task(T)`, wenn die abgeschlossene Methode eine [return](../../../language-reference/keywords/return.md)-Anweisung aufweist, die einen Wert vom Typ T zurückgibt. Verwenden Sie `Task`, wenn die abgeschlossene Methode keinen sinnvollen Wert zurückgibt. Sie können sich den `Task`-Rückgabetyp wie „Task(void)“ vorstellen.

     Weitere Informationen finden Sie unter [Async Return Types (C#) (Asynchrone Rückgabetypen (C#))](./async-return-types.md).

     Die Methode `GetURLContents` verfügt über eine return-Anweisung, und die Anweisung gibt ein Bytearray zurück. Daher ist der Rückgabetyp der der asynchronen Version „Task(T)“, wobei „T“ ein Bytearray ist. Nehmen Sie folgende Änderungen in der Methodensignatur vor:

    - Ändern Sie den Rückgabetyp zu `Task<byte[]>`.

    - Asynchrone Methoden verfügen gemäß der Konvention über Namen, die auf „Async“ enden. Benennen Sie also die Methode `GetURLContentsAsync` um.

     Im folgenden Code sind diese Änderungen dargestellt.

    ```csharp
    private async Task<byte[]> GetURLContentsAsync(string url)
    ```

     Mit diesen wenigen Änderungen ist die Konvertierung von `GetURLContents` zu einer asynchronen Methode abgeschlossen.

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a>Konvertieren von „SumPageSizes“ in eine asynchrone Methode

1. Wiederholen Sie die Schritte des vorherigen Verfahrens für `SumPageSizes`. Ändern Sie zunächst den Aufruf von `GetURLContents` zu einem asynchronen Aufruf.

    - Ändern Sie den Namen der Methode, die aufgerufen wird, von `GetURLContents` zu `GetURLContentsAsync`, sofern Sie dies nicht bereits getan haben.

    - Wenden Sie `await` auf die Aufgabe an, die durch `GetURLContentsAsync` zurückgegeben wird, um den Bytearraywert abzurufen.

     Im folgenden Code sind diese Änderungen dargestellt.

    ```csharp
    byte[] urlContents = await GetURLContentsAsync(url);
    ```

     Die vorherige Zuweisung kürzt die folgenden zwei Codezeilen.

    ```csharp
    // GetURLContentsAsync returns a Task<T>. At completion, the task
    // produces a byte array.
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //byte[] urlContents = await getContentsTask;
    ```

2. Nehmen Sie folgende Änderungen in der Methodensignatur vor:

    - Markieren Sie die Methode mit dem Modifizierer `async`.

    - Fügen Sie dem Methodennamen „Async“ hinzu.

    - Es ist dieses Mal keine Aufgabenrückgabevariable „T“ vorhanden, da `SumPageSizesAsync` keinen Wert für „T“ zurückgibt. (Die Methode weist keine `return`-Anweisung auf.) Die Methode muss jedoch eine `Task` zurückgeben, die awaitable ist. Ändern Sie daher den Rückgabetyp der Methode von `void` in `Task`.

    Im folgenden Code sind diese Änderungen dargestellt.

    ```csharp
    private async Task SumPageSizesAsync()
    ```

     Die Konvertierung von `SumPageSizes` zu `SumPageSizesAsync` ist abgeschlossen.

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a>Konvertieren von „startButton_Click“ in eine asynchrone Methode

1. Ändern Sie im Ereignishandler den Namen der aufgerufenen Methode von `SumPageSizes` zu `SumPageSizesAsync`, sofern Sie dies nicht bereits vorgenommen haben.

2. Da es sich bei `SumPageSizesAsync` um eine asynchrone Methode handelt, ändern Sie den Code im Ereignishandler, um auf das Ergebnis zu warten.

     Der Aufruf von `SumPageSizesAsync` spiegelt den Aufruf von `CopyToAsync` in `GetURLContentsAsync` wider. Der Aufruf gibt eine `Task` und keine `Task(T)` zurück.

     Analog zu den vorherigen Vorgehensweisen können Sie den Aufruf mithilfe von einer oder zwei Anweisungen konvertieren. Im folgenden Code sind diese Änderungen dargestellt.

    ```csharp
    // One-step async call.
    await SumPageSizesAsync();

    // Two-step async call.
    //Task sumTask = SumPageSizesAsync();
    //await sumTask;
    ```

3. Um den versehentlichen Neustart des Vorgangs zu verhindern, fügen Sie oben in `startButton_Click` die folgende Anweisung ein, um die Schaltfläche **Start** zu deaktivieren.

    ```csharp
    // Disable the button until the operation is complete.
    startButton.IsEnabled = false;
    ```

     Sie können die Schaltfläche am Ende des Ereignishandlers wieder aktivieren.

    ```csharp
    // Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = true;
    ```

     Weitere Informationen zum erneuten Eintreten finden Sie unter [Handling Reentrancy in Async Apps (C#) (Ablauf des erneuten Eintretens in asynchronen Anwendungen (C#))](./handling-reentrancy-in-async-apps.md).

4. Fügen Sie der Deklaration abschließend den Modifizierer `async` hinzu, sodass der Ereignishandler auf `SumPagSizesAsync` warten kann.

    ```csharp
    private async void startButton_Click(object sender, RoutedEventArgs e)
    ```

     In der Regel werden die Namen der Ereignishandler nicht geändert. Der Rückgabetyp wird nicht zu `Task` geändert, da Ereignishandler `void` zurückgeben müssen.

     Die Konvertierung des Projekts von der synchronen zu asynchronen Verarbeitung ist abgeschlossen.

## <a name="test-the-asynchronous-solution"></a>Testen der asynchronen Lösung

1. Drücken Sie die Taste **F5**, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Start**.

2. Es sollte eine Ausgabe angezeigt werden, die der Ausgabe der synchronen Lösung gleicht. Folgende Unterschiede sind jedoch zu berücksichtigen.

    - Die Ergebnisse treten nicht alle gleichzeitig auf, nachdem die Verarbeitung abgeschlossen wurde. Beispielsweise enthalten beide Programme eine Zeile in `startButton_Click`, die das Textfeld löscht. Es ist vorgesehen, das Textfeld zwischen zwei Ausführungen zu löschen, wenn Sie die Schaltfläche **Start** ein zweites Mal auswählen, nachdem ein Ergebnissatz angezeigt wurde. In der synchronen Version wird das Textfeld unmittelbar vor der zweiten Anzeige des Zählers gelöscht, wenn die Downloads abgeschlossen sind und der UI-Thread für die Verarbeitung anderer Aktionen frei ist. In der asynchronen Version wird das Textfeld unmittelbar gelöscht, nachdem Sie die Schaltfläche **Start** ausgewählt haben.

    - Das Wichtigste ist jedoch, dass der UI-Thread nicht blockiert wird, während Downloads vorgenommen werden. Sie können das Fenster verschieben oder dessen Größe anpassen, während die Webressourcen heruntergeladen, gezählt und angezeigt werden. Wenn eine der Websites langsam ist oder nicht antwortet, können Sie den Vorgang abbrechen, indem Sie die Schaltfläche **Schließen** (das x im roten Feld in der oberen rechten Ecke) auswählen.

## <a name="replace-method-geturlcontentsasync-with-a-net-framework-method"></a>Ersetzen der Methode „GetURLContentsAsync“ durch eine .NET Framework-Methode

1. .NET Framework 4.5 bietet viele asynchrone Methoden, die Sie verwenden können. Eine davon, die <xref:System.Net.Http.HttpClient>-Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> erfüllt genau das, was in dieser exemplarischen Vorgehensweise nötig ist. Sie können sie anstelle der `GetURLContentsAsync`-Methode verwenden, die Sie in einer vorherigen Vorgehensweise erstellt haben.

     Der erste Schritt besteht darin, ein `HttpClient`-Objekt in der Methode `SumPageSizesAsync` zu erstellen. Fügen Sie am Anfang der Methode die folgende Deklaration hinzu.

    ```csharp
    // Declare an HttpClient object and increase the buffer size. The
    // default buffer size is 65,536.
    HttpClient client =
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };
    ```

2. Ersetzen Sie in `SumPageSizesAsync,` den Aufruf zu Ihrer `GetURLContentsAsync`-Methode durch einen Aufruf zur Methode `HttpClient`.

    ```csharp
    byte[] urlContents = await client.GetByteArrayAsync(url);
    ```

3. Entfernen Sie die von Ihnen geschriebene `GetURLContentsAsync`-Methode, oder kommentieren Sie sie aus.

4. Drücken Sie die Taste **F5**, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Start**.

     Das Verhalten dieser Version des Projekts sollte mit dem Verhalten übereinstimmen, das in der Vorgehensweise „So testen Sie die asynchrone Lösung“ beschrieben wird, es sollte aber weniger Aufwand Ihrerseits nötig sein.

## <a name="example-code"></a>Beispielcode

Der folgende Code enthält das vollständige Beispiel der Konvertierung von einer synchronen zu einer asynchronen Lösung mithilfe der von Ihnen geschriebenen asynchronen `GetURLContentsAsync`-Methode. Beachten Sie, dass sie der ursprünglichen synchronen Lösung sehr stark ähnelt.

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

// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            resultsTextBox.Clear();

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                byte[] urlContents = await GetURLContentsAsync(url);

                // The previous line abbreviates the following two assignment statements.

                // GetURLContentsAsync returns a Task<T>. At completion, the task
                // produces a byte array.
                //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }
            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())

            // The previous statement abbreviates the following two statements.

            //Task<WebResponse> responseTask = webReq.GetResponseAsync();
            //using (WebResponse response = await responseTask)
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    // Read the bytes in responseStream and copy them to content.
                    await responseStream.CopyToAsync(content);

                    // The previous statement abbreviates the following two statements.

                    // CopyToAsync returns a Task, not a Task<T>.
                    //Task copyTask = responseStream.CopyToAsync(content);

                    // When copyTask is completed, content contains a copy of
                    // responseStream.
                    //await copyTask;
                }
            }
            // Return the result as a byte array.
            return content.ToArray();
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

Der folgende Code umfasst das vollständige Beispiel der Lösung, die die `HttpClient`-Methode `GetByteArrayAsync` verwendet.

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

// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            // One-step async call.
            await SumPageSizesAsync();

            //// Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client =
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                // GetByteArrayAsync returns a task. At completion, the task
                // produces a byte array.
                byte[] urlContents = await client.GetByteArrayAsync(url);

                // The following two lines can replace the previous assignment statement.
                //Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="see-also"></a>Siehe auch

- [Async Sample: Webzugriff – Exemplarische Vorgehensweise (C# und Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/hh300224(v=vs.110))
- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
- [Asynchrone Programmierung mit „async“ und „await“ (C#)](./index.md)
- [Asynchrone Rückgabetypen (C#)](./async-return-types.md)
- [Task-based Asynchronous Programming (TAP) (Aufgabenbasiertes asynchrones Programmieren (TAP))](https://www.microsoft.com/download/details.aspx?id=19957)
- [Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
- [Vorgehensweise: Paralleles Erstellen mehrerer Webanforderungen mit Async und Await (C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
