---
title: Asynchrone Aufgaben nach einer Zeitperiode abbrechen (C#)
description: Verwenden Sie die Methode CancellationTokenSource.CancelAfter in C#, um den Abbruch aller zugeordneten Aufgaben zu planen, die in diesem Beispiel nicht innerhalb eines Zeitraums abgeschlossen wurden.
ms.date: 07/20/2015
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: f32af1d893c60ac17648f60fa3aa90adaa0383e8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925291"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a>Asynchrone Aufgaben nach einer Zeitperiode abbrechen (C#)

Sie können einen asynchronen Vorgang nach einem gewissen Zeitraum mithilfe der <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType>-Methode abbrechen, wenn Sie nicht auf das Ende des Vorgangs warten möchten. Diese Methode plant den Abbruch aller zugeordneten Aufgaben, die innerhalb des vom `CancelAfter`-Ausdruck festgelegten Zeitraums nicht abgeschlossen sind.

Dieses Beispiel fügt dem in [Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) entwickelten Code Funktionen zum Herunterladen einer Liste von Websites und Anzeigen der Länge der Inhalte jeder Site hinzu.

> [!NOTE]
> Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.

## <a name="download-the-example"></a>Herunterladen des Beispiels

Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und die folgenden Schritte ausführen.

1. Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.

2. Wählen Sie auf der Menüleiste **Datei** > **Öffnen** > **Projekt/Projektmappe** aus.

3. Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningCS.

4. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelAfterTime**-Projekt und wählen dann **Als Startprojekt festlegen** aus.

5. Drücken Sie die Taste **F5**, um das Projekt auszuführen. (Oder drücken Sie **STRG**+**F5**, um das Projekt auszuführen, ohne es zu debuggen.)

6. Führen Sie das Programm mehrmals aus, und überprüfen Sie dabei, ob die Ausgabe für alle, keine oder einige Websites angezeigt wird.

Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich die Dateien „MainWindow.xaml.vb“ und „MainWindow.xaml.cs“ am Ende dieses Themas anschauen.

## <a name="build-the-example"></a>Erstellen des Beispiels

Das Beispiel in diesem Thema baut auf dem Projekt auf, das unter [Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) entwickelt wurde, um eine Aufgabenliste abzubrechen. Im Beispiel wird die gleiche UI verwendet, obwohl die Schaltfläche **Abbrechen** nicht explizit verwendet wird.

Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelAListOfTasks** aus. Fügen Sie diesem Projekt die Änderungen in diesem Thema hinzu.

Zum Angeben einer maximalen Zeitspanne bis zum Abbrechen der Aufgaben fügen Sie den Aufruf von `CancelAfter` in `startButton_Click` hinzu, wie im folgenden Beispiel gezeigt. Die Ergänzung ist mit Sternchen gekennzeichnet.

```csharp
private async void startButton_Click(object sender, RoutedEventArgs e)
{
    // Instantiate the CancellationTokenSource.
    cts = new CancellationTokenSource();

    resultsTextBox.Clear();

    try
    {
        // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
        // can adjust the time.)
        cts.CancelAfter(2500);

        await AccessTheWebAsync(cts.Token);
        resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
    }
    catch (OperationCanceledException)
    {
        resultsTextBox.Text += "\r\nDownloads canceled.\r\n";
    }
    catch (Exception)
    {
        resultsTextBox.Text += "\r\nDownloads failed.\r\n";
    }

    cts = null;
}
```

 Führen Sie das Programm mehrmals aus, und überprüfen Sie dabei, ob die Ausgabe für alle, keine oder einige Websites angezeigt wird. Die folgende Ausgabe ist beispielhaft.

```output
Length of the downloaded string: 35990.

Length of the downloaded string: 407399.

Length of the downloaded string: 226091.

Downloads canceled.
```

## <a name="complete-example"></a>Vollständiges Beispiel

Der folgende Code besteht aus dem vollständigen Text der Datei „MainWindow.xaml.cs“ für das Beispiel. Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.

Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.

Sie können das Projekt hier herunterladen: [Async Sample: Fine Tuning Your Application (Async-Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).

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

// Add the following using directive.
using System.Threading;

namespace CancelAfterTime
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
                // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
                // can adjust the time.)
                cts.CancelAfter(2500);

                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.\r\n";
            }

            cts = null;
        }

        // You can still include a Cancel button if you want to.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // Note that the Cancel button cancels all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Sample Output:

    // Length of the downloaded string: 35990.

    // Length of the downloaded string: 407399.

    // Length of the downloaded string: 226091.

    // Downloads canceled.
}
```

## <a name="see-also"></a>Siehe auch

- [Asynchrone Programmierung mit „async“ und „await“ (C#)](./index.md)
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Cancel an Async Task or a List of Tasks (C#) (Abbrechen einer asynchronen Aufgabe oder Aufgabenliste (C#))](./cancel-an-async-task-or-a-list-of-tasks.md)
- [Feinabstimmung der Async-Anwendung (C#)](./fine-tuning-your-async-application.md)
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Asynchrones Beispiel: Feinabstimmung Ihrer Anwendung)
