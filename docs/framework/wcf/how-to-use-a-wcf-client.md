---
title: 'Tutorial: Verwenden Sie einen Windows Communication Foundation-client'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 4d883277f795ea84c59aee91ffcb9b9802b0933b
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411719"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>Tutorial: Verwenden Sie einen Windows Communication Foundation-client

In diesem Tutorial wird beschrieben, die letzte von fünf Aufgaben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Lernprogramme, finden Sie unter [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).

Nachdem Sie erstellt und einen Windows Communication Foundation (WCF)-Proxy konfiguriert haben, erstellen Sie eine Clientinstanz, und Sie kompilieren Sie die Clientanwendung. Damit können Sie dann mit dem WCF-Dienst kommunizieren. 

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Fügen Sie Code, um den WCF-Client verwenden.
> - Testen Sie den WCF-Client.

## <a name="add-code-to-use-the-wcf-client"></a>Hinzufügen von Code zum Verwenden des WCF-Clients

Der Clientcode führt die folgenden Schritte aus:
- Instanziiert den WCF-Client.
- Die Dienstoperationen werden vom erstellten Proxy aufgerufen.
- Der Client wird geschlossen, nachdem der Vorgangsaufruf abgeschlossen wurde.

Öffnen der **"Program.cs"** oder **"Module1.vb"** -Datei aus dem **"gettingstartedclient"** Projekts, und Ersetzen Sie den Code durch den folgenden Code:

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
Imports System
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

Beachten Sie, dass die `using` (für Visual C#) oder `Imports` (für Visual Basic)-Anweisung, die importiert `GettingStartedClient.ServiceReference1`. Diese Anweisung importiert den Code, der mit Visual Studio generiert die **Hinzufügen eines Dienstverweises** Funktion. Der Code instanziiert den WCF-Proxy und ruft alle Dienstvorgänge, die vom rechnerdienst verfügbar macht. Klicken Sie dann den Proxy schließt, und das Programm beendet wird.

## <a name="test-the-wcf-client"></a>Testen des WCF-Clients

### <a name="test-the-application-from-visual-studio"></a>Testen Sie die Anwendung aus Visual Studio

1. Speichern Sie und erstellen Sie die Projektmappe.

2. Wählen Sie die **GettingStartedLib** Ordner, und wählen Sie dann **als Startprojekt festlegen** aus dem Kontextmenü.

3. Von **Startprojekte**Option **GettingStartedLib** aus der Dropdown-Liste, und wählen Sie dann **ausführen** , oder drücken Sie **F5**.

### <a name="test-the-application-from-a-command-prompt"></a>Testen Sie die Anwendung über eine Eingabeaufforderung

1. Öffnen Sie eine Eingabeaufforderung als Administrator, und navigieren Sie zu Ihrem Verzeichnis der Visual Studio-Projektmappe. 

2. Zum Starten des Diensts: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.

3. Um den Client zu starten: Öffnen Sie eine andere Eingabeaufforderung, navigieren Sie zu Ihrem Verzeichnis der Visual Studio-Projektmappe, und geben Sie *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.

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

Sie haben jetzt alle Aufgaben in der WCF-erste-Schritte-Lernprogramm abgeschlossen. In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Fügen Sie Code, um den WCF-Client verwenden.
> - Testen Sie den WCF-Client.

Wenn Sie Probleme oder Fehler in einem beliebigen Schritt verfügen, führen Sie die Schritte in den Artikel zur Problembehandlung, um sie zu korrigieren.

> [!div class="nextstepaction"]
> [Problembehandlung bei den Get Schritte mit WCF-Lernprogramme](troubleshooting-the-getting-started-tutorial.md)

