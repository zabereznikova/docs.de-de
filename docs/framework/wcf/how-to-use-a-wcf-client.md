---
title: 'Tutorial: Verwenden eines Windows Communication Foundation Clients'
description: Erfahren Sie, wie Sie eine Client Instanz erstellen, die Anwendung kompilieren und mit einem Dienst im Rahmen einer Reihe von Artikeln über das Erstellen einer WCF-Anwendung kommunizieren.
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 5c94d5f8af679580c4194aaaadeda759098953d2
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244334"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>Tutorial: Verwenden eines Windows Communication Foundation Clients

In diesem Tutorial werden die letzten fünf Aufgaben beschrieben, die zum Erstellen einer Basic Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Einstieg in Windows Communication Foundation Anwendungen](getting-started-tutorial.md).

Nachdem Sie einen Windows Communication Foundation (WCF)-Proxy erstellt und konfiguriert haben, erstellen Sie eine Client Instanz, und kompilieren Sie die Client Anwendung. Anschließend verwenden Sie Sie, um mit dem WCF-Dienst zu kommunizieren.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Fügen Sie Code zur Verwendung des WCF-Clients hinzu.
> - Testen Sie den WCF-Client.

## <a name="add-code-to-use-the-wcf-client"></a>Hinzufügen von Code zur Verwendung des WCF-Clients

Der Client Code führt die folgenden Schritte aus:

- Instanziiert den WCF-Client.
- Die Dienstoperationen werden vom erstellten Proxy aufgerufen.
- Schließt den Client, nachdem der Vorgang aufgerufen wurde.

Öffnen Sie die Datei **Program.cs** oder **Module1. vb** aus dem **gettingstartedclient** -Projekt, und ersetzen Sie den Code durch den folgenden Code:

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

Beachten Sie die- `using` Anweisung (für Visual c#) oder die- `Imports` Anweisung (for Visual Basic), die importiert `GettingStartedClient.ServiceReference1` . Diese Anweisung importiert den Code, der von Visual Studio mit der **Dienstverweis hinzufügen** -Funktion generiert wurde. Der Code instanziiert den WCF-Proxy und ruft jeden der Dienst Vorgänge auf, die der Rechner Dienst verfügbar macht. Anschließend wird der Proxy geschlossen und das Programm beendet.

## <a name="test-the-wcf-client"></a>Testen des WCF-Clients

### <a name="test-the-application-from-visual-studio"></a>Testen der Anwendung in Visual Studio

1. Speichern und erstellen Sie die Projektmappe.

2. Wählen Sie den Ordner **gettingstartedlib** aus, und wählen Sie dann im Kontextmenü die Option **als Startprojekt festlegen** aus.

3. Wählen Sie in **Start Projekten**in der Dropdown Liste **gettingstartedlib** aus, und wählen Sie dann **Ausführen** aus, oder drücken Sie **F5**.

### <a name="test-the-application-from-a-command-prompt"></a>Testen der Anwendung über eine Eingabeaufforderung

1. Öffnen Sie eine Eingabeaufforderung als Administrator, und navigieren Sie dann zu Ihrem Visual Studio-Projektmappenverzeichnis.

2. Geben Sie *GettingStartedHost\bin\Debug\GettingStartedHost.exe*ein, um den Dienst zu starten.

3. So starten Sie den-Client: Öffnen Sie eine andere Eingabeaufforderung, navigieren Sie zu Ihrem Visual Studio-Projektmappenverzeichnis, und geben Sie *GettingStartedClient\bin\Debug\GettingStartedClient.exe*

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

Sie haben jetzt alle Aufgaben im WCF-Tutorial "Get Started" abgeschlossen. In diesem Tutorial haben Sie Folgendes gelernt:

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Fügen Sie Code zur Verwendung des WCF-Clients hinzu.
> - Testen Sie den WCF-Client.

Wenn in einem der Schritte Probleme oder Fehler auftreten, führen Sie die Schritte im Artikel zur Problembehandlung aus, um Sie zu beheben.

> [!div class="nextstepaction"]
> [Behandeln von Problemen mit den Tutorials für die ersten Schritte mit WCF](troubleshooting-the-getting-started-tutorial.md)
