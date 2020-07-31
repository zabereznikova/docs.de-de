---
title: Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#)
description: Verwenden Sie diese Beispiele, um eine Schaltfläche hinzuzufügen, die das Ausführen einer asynchronen Anwendung vor dem Abschluss abbricht. Diese C#-Anwendung lädt den Inhalt einer oder mehrerer Websites herunter.
ms.date: 07/20/2015
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 21bdbc3bc7c3b752fab160429d71356fb87d9976
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925345"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-c"></a>Abbrechen einer asynchronen Aufgabe oder Aufgabenliste (C#)

Sie können eine Schaltfläche einrichten, über die Sie eine asynchrone Anwendung abbrechen können, wenn Sie nicht darauf warten möchten, bis diese beendet wird. Anhand der Beispiele in diesem Thema können Sie einer Anwendung, über die der Inhalt einer Website oder einer Liste von Websites heruntergeladen wird, eine Schaltfläche zum Abbrechen hinzufügen.

In den Beispielen wird die Benutzeroberfläche verwendet, die in [Feinabstimmung der Async-Anwendung (C#)](./fine-tuning-your-async-application.md) beschrieben wird.

> [!NOTE]
> Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.

## <a name="cancel-a-task"></a>Abbrechen einer Aufgabe

Im ersten Beispiel wird die Schaltfläche **Abbrechen** einer Aufgabe mit einem einzigen Download zugeordnet. Wenn Sie die Schaltfläche auswählen, während die Anwendung Inhalt herunterlädt, wird der Download abgebrochen.

### <a name="download-the-example"></a>Herunterladen des Beispiels

Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und die folgenden Schritte ausführen.

1. Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.

2. Wählen Sie auf der Menüleiste **Datei** > **Öffnen** > **Projekt/Projektmappe** aus.

3. Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningCS.

4. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelATask**-Projekt, und wählen Sie dann **Als Startprojekt festlegen** aus.

5. Wählen Sie die Taste **F5** aus, um das Projekt auszuführen (oder drücken Sie **STRG**+**F5**, um das Projekt ohne Debuggen auszuführen).

> [!TIP]
> Wenn Sie das Projekt nicht herunterladen möchten, können Sie die „MainWindow.xaml.cs“-Dateien am Ende dieses Themas überprüfen.

### <a name="build-the-example"></a>Erstellen des Beispiels
 Mit den folgenden Änderungen wird eine Schaltfläche **Abbrechen** zu einer Anwendung hinzugefügt, die eine Website herunterlädt. Wenn Sie das Beispiel nicht herunterladen oder erstellen möchten, können Sie sich das Endprodukt im Abschnitt „Vollständige Beispiele“ am Ende dieses Themas ansehen. Die Änderungen im Code sind mit Sternchen gekennzeichnet.

 Um das Beispiel selbst zu erstellen, befolgen Sie Schritt für Schritt die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **StarterCode** anstelle von **CancelATask** aus.

 Fügen Sie dann der Datei „MainWindow.xaml.cs“ dieses Projekts die folgenden Änderungen hinzu.

1. Deklarieren Sie eine `CancellationTokenSource`-Variable, `cts`, die im Bereich für alle Methoden liegt, die darauf zugreifen.

    ```csharp
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. Fügen Sie den folgenden Ereignishandler für die Schaltfläche **Abbrechen** hinzu. Der Ereignishandler verwendet die <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType>-Methode, um `cts` bei Abbruchanforderungen durch den Benutzer zu benachrichtigen.

    ```csharp
    // ***Add an event handler for the Cancel button.
    private void cancelButton_Click(object sender, RoutedEventArgs e)
    {
        if (cts != null)
        {
            cts.Cancel();
        }
    }
    ```

3. Nehmen Sie die folgenden Änderungen in `startButton_Click` vor, dem Ereignishandler für die Schaltfläche **Start**.

    - Instanziieren Sie die `CancellationTokenSource`, `cts`.

        ```csharp
        // ***Instantiate the CancellationTokenSource.
        cts = new CancellationTokenSource();
        ```

    - Senden Sie im Aufruf von `AccessTheWebAsync`, wodurch der Inhalt einer bestimmten Website heruntergeladen wird, die <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType>-Eigenschaft von `cts` als Argument. Die `Token`-Eigenschaft gibt die Meldung weiter, wenn ein Abbruch angefordert wird. Fügen Sie einen catch-Block hinzu, der eine Meldung angezeigt, wenn der Benutzer den Downloadvorgang abbrechen möchte. Im folgende Code sind alle Änderungen dargestellt.

        ```csharp
        try
        {
            // ***Send a token to carry the message if cancellation is requested.
            int contentLength = await AccessTheWebAsync(cts.Token);
            resultsTextBox.Text += $"\r\nLength of the downloaded string: {contentLength}.\r\n";
        }
        // *** If cancellation is requested, an OperationCanceledException results.
        catch (OperationCanceledException)
        {
            resultsTextBox.Text += "\r\nDownload canceled.\r\n";
        }
        catch (Exception)
        {
            resultsTextBox.Text += "\r\nDownload failed.\r\n";
        }
        ```

4. Verwenden Sie in `AccessTheWebAsync` die <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> - Überladung der `GetAsync`-Methode im <xref:System.Net.Http.HttpClient>-Typ, um den Inhalt einer Website herunterzuladen. Übergeben Sie `ct`, der <xref:System.Threading.CancellationToken>-Parameter von `AccessTheWebAsync`, als zweites Argument. Das Token enthält die Meldung, wenn der Benutzer die Schaltfläche **Abbrechen** auswählt.

     Im folgende Code sind die Änderungen in `AccessTheWebAsync` dargestellt.

    ```csharp
    // ***Provide a parameter for the CancellationToken.
    async Task<int> AccessTheWebAsync(CancellationToken ct)
    {
        HttpClient client = new HttpClient();

        resultsTextBox.Text += "\r\nReady to download.\r\n";

        // You might need to slow things down to have a chance to cancel.
        await Task.Delay(250);

        // GetAsync returns a Task<HttpResponseMessage>.
        // ***The ct argument carries the message if the Cancel button is chosen.
        HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        // The result of the method is the length of the downloaded website.
        return urlContents.Length;
    }
    ```

5. Wenn Sie das Programm nicht abbrechen, wird folgende Ausgabe erzeugt.

    ```text
    Ready to download.
    Length of the downloaded string: 158125.
    ```

     Wenn Sie die Schaltfläche **Abbrechen** auswählen, bevor das Programm das Herunterladen des Inhalts abgeschlossen hat, erzeugt das Programm die folgende Ausgabe.

    ```text
    Ready to download.
    Download canceled.
    ```

## <a name="cancel-a-list-of-tasks"></a>Abbrechen einer Aufgabenliste

Sie können das vorherige Beispiel so erweitern, dass viele Aufgaben abgebrochen werden, indem Sie jeder Aufgabe die gleiche `CancellationTokenSource`-Instanz zuordnen. Wenn Sie die Schaltfläche **Abbrechen** auswählen, brechen Sie alle Aufgaben ab, die noch nicht abgeschlossen sind.

### <a name="download-the-example"></a>Herunterladen des Beispiels

Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und die folgenden Schritte ausführen.

1. Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.

2. Wählen Sie auf der Menüleiste **Datei** > **Öffnen** > **Projekt/Projektmappe** aus.

3. Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningCS.

4. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelAListOfTasks**-Projekt, und wählen Sie dann **Als Startprojekt festlegen** aus.

5. Drücken Sie die Taste **F5**, um das Projekt auszuführen.

     Drücken Sie die Tasten **STRG**+**F5**, um das Projekt auszuführen, ohne es zu debuggen.

Wenn Sie das Projekt nicht herunterladen möchten, können Sie die „MainWindow.xaml.cs“-Dateien am Ende dieses Themas überprüfen.

### <a name="build-the-example"></a>Erstellen des Beispiels

Um das Beispiel selbst zu erweitern, befolgen Sie Schritt für Schritt die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelATask** aus. Fügen Sie die folgenden Änderungen zu diesem Projekt hinzu. Die Änderungen im Programm sind mit Sternchen gekennzeichnet.

1. Fügen Sie eine Methode hinzu, um eine Liste von Webadressen zu erstellen.

    ```csharp
    // ***Add a method that creates a list of web addresses.
    private List<string> SetUpURLList()
    {
        List<string> urls = new List<string>
        {
            "https://msdn.microsoft.com",
            "https://msdn.microsoft.com/library/hh290138.aspx",
            "https://msdn.microsoft.com/library/hh290140.aspx",
            "https://msdn.microsoft.com/library/dd470362.aspx",
            "https://msdn.microsoft.com/library/aa578028.aspx",
            "https://msdn.microsoft.com/library/ms404677.aspx",
            "https://msdn.microsoft.com/library/ff730837.aspx"
        };
        return urls;
    }
    ```

2. Rufen Sie die Methode in `AccessTheWebAsync` auf.

    ```csharp
    // ***Call SetUpURLList to make a list of web addresses.
    List<string> urlList = SetUpURLList();
    ```

3. Fügen Sie die folgende Schleife in `AccessTheWebAsync` hinzu, um jede Webadresse in der Liste zu verarbeiten.

    ```csharp
    // ***Add a loop to process the list of web addresses.
    foreach (var url in urlList)
    {
        // GetAsync returns a Task<HttpResponseMessage>.
        // Argument ct carries the message if the Cancel button is chosen.
        // ***Note that the Cancel button can cancel all remaining downloads.
        HttpResponseMessage response = await client.GetAsync(url, ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
    }
    ```

4. Da `AccessTheWebAsync` die Längen anzeigt, muss die Methode nichts zurückzugeben. Entfernen Sie die return-Anweisung, und ändern Sie den Rückgabetyp der Methode in <xref:System.Threading.Tasks.Task> anstelle von <xref:System.Threading.Tasks.Task%601>.

    ```csharp
    async Task AccessTheWebAsync(CancellationToken ct)
    ```

     Rufen Sie die Methode über `startButton_Click` auf, indem Sie eine Anweisung anstelle eines Ausdrucks verwenden.

    ```csharp
    await AccessTheWebAsync(cts.Token);
    ```

5. Wenn Sie das Programm nicht abbrechen, wird folgende Ausgabe erzeugt.

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Length of the downloaded string: 158124.

    Length of the downloaded string: 204890.

    Length of the downloaded string: 175488.

    Length of the downloaded string: 145790.

    Downloads complete.
    ```

     Wenn Sie die Schaltfläche **Abbrechen** auswählen, bevor die Downloads abgeschlossen sind, enthält die Ausgabe die Längen der Downloads, die vor dem Abbruch abgeschlossen wurden.

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="complete-examples"></a>Vollständige Beispiele

Die folgenden Abschnitte enthalten den Code für jedes der vorherigen Beispiele. Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.

Sie können die Projekte hier herunterladen: [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen.

### <a name="example---cancel-a-task"></a>Beispiel: Abbrechen einer Aufgabe

Der folgende Code ist die vollständige Datei „MainWindow.xaml.cs“ für das Beispiel, in dem eine einzelne Aufgabe abgebrochen wird.

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

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive for System.Threading.

using System.Threading;
namespace CancelATask
{
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // ***Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            resultsTextBox.Clear();

            try
            {
                // ***Send a token to carry the message if cancellation is requested.
                int contentLength = await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }
            // *** If cancellation is requested, an OperationCanceledException results.
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownload canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownload failed.\r\n";
            }

            // ***Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // ***Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // ***Provide a parameter for the CancellationToken.
        async Task<int> AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            resultsTextBox.Text += "\r\nReady to download.\r\n";

            // You might need to slow things down to have a chance to cancel.
            await Task.Delay(250);

            // GetAsync returns a Task<HttpResponseMessage>.
            // ***The ct argument carries the message if the Cancel button is chosen.
            HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            // The result of the method is the length of the downloaded website.
            return urlContents.Length;
        }
    }

    // Output for a successful download:

    // Ready to download.

    // Length of the downloaded string: 158125.

    // Or, if you cancel:

    // Ready to download.

    // Download canceled.
}
```

### <a name="example---cancel-a-list-of-tasks"></a>Beispiel: Abbrechen einer Aufgabenliste

Der folgende Code ist die vollständige Datei „MainWindow.xaml.cs“ für das Beispiel, in dem eine Aufgabenliste abgebrochen wird.

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

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive for System.Threading.
using System.Threading;

namespace CancelAListOfTasks
{
    public partial class MainWindow : Window
    {
        // Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            resultsTextBox.Clear();

            try
            {
                await AccessTheWebAsync(cts.Token);
                // ***Small change in the display lines.
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.";
            }

            // Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // Provide a parameter for the CancellationToken.
        // ***Change the return type to Task because the method has no return statement.
        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // ***Call SetUpURLList to make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Add a loop to process the list of web addresses.
            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // ***Note that the Cancel button can cancel all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        // ***Add a method that creates a list of web addresses.
        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Output if you do not choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Length of the downloaded string: 158124.

    //Length of the downloaded string: 204890.

    //Length of the downloaded string: 175488.

    //Length of the downloaded string: 145790.

    //Downloads complete.

    // Sample output if you choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Downloads canceled.
}
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [Asynchrone Programmierung mit „async“ und „await“ (C#)](./index.md)
- [Feinabstimmung der Async-Anwendung (C#)](./fine-tuning-your-async-application.md)
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Asynchrones Beispiel: Feinabstimmung Ihrer Anwendung)
