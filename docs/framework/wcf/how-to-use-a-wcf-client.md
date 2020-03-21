---
title: 'Tutorial: Verwenden eines Windows Communication Foundation-Clients'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: d2357c134aef8da204dcdb19d6c1fc93cfdc068c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184009"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>Tutorial: Verwenden eines Windows Communication Foundation-Clients

In diesem Tutorial wird die letzte von fünf Aufgaben beschrieben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).

Nachdem Sie einen Windows Communication Foundation (WCF)-Proxy erstellt und konfiguriert haben, erstellen Sie eine Clientinstanz und kompilieren die Clientanwendung. Anschließend verwenden Sie es, um mit dem WCF-Dienst zu kommunizieren.

In diesem Tutorial lernen Sie Folgendes:
> [!div class="checklist"]
>
> - Fügen Sie Code hinzu, um den WCF-Client zu verwenden.
> - Testen Sie den WCF-Client.

## <a name="add-code-to-use-the-wcf-client"></a>Hinzufügen von Code zur Verwendung des WCF-Clients

Der Clientcode führt die folgenden Schritte aus:

- Instanziiert den WCF-Client.
- Die Dienstoperationen werden vom erstellten Proxy aufgerufen.
- Schließt den Client, nachdem der Vorgangsaufruf abgeschlossen wurde.

Öffnen Sie die **Datei Program.cs** oder **Module1.vb** aus dem **GettingStartedClient-Projekt,** und ersetzen Sie ihren Code durch den folgenden Code:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
            // Call the Add service operation.
            double value1 = 100.00D;
            double value2 = 15.99D;
            double result = client.Add(value1, value2);
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

            // Call the Subtract service operation.
            value1 = 145.00D;
            value2 = 76.54D;
            result = client.Subtract(value1, value2);
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

            // Call the Multiply service operation.
            value1 = 9.00D;
            value2 = 81.25D;
            result = client.Multiply(value1, value2);
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

            // Call the Divide service operation.
            value1 = 22.00D;
            value2 = 7.00D;
            result = client.Divide(value1, value2);
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

            // Step 3: Close the client to gracefully close the connection and clean up resources.
            Console.WriteLine("\nPress <Enter> to terminate the client.");
            Console.ReadLine();
            client.Close();
        }
    }
}
```

```vb
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClient.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy.
        Dim Client As New CalculatorClient()

        ' Step 2: Call the service operations.
        ' Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        ' Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        ' Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        ' Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Close the client to gracefully close the connection and clean up resources.
        Console.WriteLine()
        Console.WriteLine("Press <Enter> to terminate the client.")
        Console.ReadLine()
        Client.Close()

    End Sub

End Module
```

Beachten `using` Sie die (für `Imports` Visual C) oder (für Visual Basic) Anweisung, die importiert. `GettingStartedClient.ServiceReference1` Diese Anweisung importiert den Code, den Visual Studio mit der Funktion **Dienstreferenz hinzufügen** generiert hat. Der Code instanziiert den WCF-Proxy und ruft jeden dienstbetrieb auf, den der Rechnerdienst verfügbar macht. Anschließend wird der Proxy geschlossen und das Programm beendet.

## <a name="test-the-wcf-client"></a>Testen des WCF-Clients

### <a name="test-the-application-from-visual-studio"></a>Testen der Anwendung in Visual Studio

1. Speichern und erstellen Sie die Projektmappe.

2. Wählen Sie den Ordner **GettingStartedLib** aus, und wählen Sie dann im Kontextmenü **Als Startprojekt festlegen** aus.

3. Wählen Sie unter **Startprojekte** **aus GettingStartedLib** aus der Dropdown-Liste aus, und wählen Sie dann **Ausführen** oder drücken Sie **F5**.

### <a name="test-the-application-from-a-command-prompt"></a>Testen der Anwendung über eine Eingabeaufforderung

1. Öffnen Sie eine Eingabeaufforderung als Administrator, und navigieren Sie dann zu Ihrem Visual Studio-Lösungsverzeichnis.

2. So starten Sie den Dienst: Geben Sie *GettingStartedHost-Bin-Debug-,GettingStartedHost.exe*ein.

3. So starten Sie den Client: Öffnen Sie eine weitere Eingabeaufforderung, navigieren Sie zu Ihrem Visual Studio-Lösungsverzeichnis, und geben Sie dann *GettingStartedClient-Bin-Debug-GettingStartedClient.exe*ein.

   *GettingStartedHost.exe* erzeugt die folgende Ausgabe:

   ```text
   The service is ready.
   Press <Enter> to terminate the service.

   Received Add(100,15.99)
   Return: 115.99
   Received Subtract(145,76.54)
   Return: 68.46
   Received Multiply(9,81.25)
   Return: 731.25
   Received Divide(22,7)
   Return: 3.14285714285714
   ```

   *GettingStartedClient.exe* erzeugt die folgende Ausgabe:

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a>Nächste Schritte

Sie haben nun alle Aufgaben im WCF-Lernprogramm "Get started" abgeschlossen. In diesem Tutorial haben Sie Folgendes gelernt:

In diesem Tutorial lernen Sie Folgendes:
> [!div class="checklist"]
>
> - Fügen Sie Code hinzu, um den WCF-Client zu verwenden.
> - Testen Sie den WCF-Client.

Wenn in einem der Schritte Probleme oder Fehler auftreten, führen Sie die Schritte im Artikel zur Problembehandlung aus, um diese zu beheben.

> [!div class="nextstepaction"]
> [Beheben der Ersten Schritte mit WCF-Tutorials](troubleshooting-the-getting-started-tutorial.md)
