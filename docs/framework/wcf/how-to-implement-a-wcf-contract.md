---
title: 'Tutorial: Implementieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: fa8c5457c636d7f37215f0d4b4fdbb1c96c9481e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929052"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Tutorial: Implementieren eines Windows Communication Foundation-Dienstvertrags

In diesem Tutorial wird beschrieben, die zweite von fünf Schritte zur Erstellung einer grundlegenden Windows Communication Foundation (WCF)-Anwendung. Eine Übersicht über die Lernprogramme, finden Sie unter [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).

Der nächste Schritt zum Erstellen einer WCF-Anwendung ist, Code hinzufügen, um die WCF-Dienstschnittstelle implementiert, die Sie im vorherigen Schritt erstellt haben. In diesem Schritt erstellen Sie eine Klasse namens `CalculatorService` , implementiert der benutzerdefinierte `ICalculator` Schnittstelle. Jede Methode in der folgende Code Ruft eine rechnervorgang und schreibt Text in der Konsole, um sie zu testen. 

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Fügen Sie Code zum Implementieren des WCF-Dienstvertrags.
> - Erstellen Sie die Projektmappe.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Hinzufügen von Code zum Implementieren des WCF-Dienstvertrags

In **GettingStartedLib**öffnen die **Service1.cs** oder **Service1.vb** -Datei und Ersetzen Sie den Code durch den folgenden Code:

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

## <a name="edit-appconfig"></a>Bearbeiten Sie die Datei "App.config"

Bearbeiten Sie **"App.config"** in **GettingStartedLib** entsprechend die Änderungen, die Sie am Code vorgenommen.
- Für visuelle C# Projekte:
  - Ändern Sie Zeile 14 `<service name="GettingStartedLib.CalculatorService">`
  - Ändern Sie Zeile 17 in `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Ändern Sie Zeile 22 in `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Für Visual Basic-Projekte:
  - Ändern Sie Zeile 14 `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Ändern Sie Zeile 17 in `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Ändern Sie Zeile 22 in `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Kompilieren des Codes

Erstellen Sie die Projektmappe aus, um sicherzustellen, dass Kompilierungsfehler vorhanden sind. Wenn Sie Visual Studio verwenden, sind die **erstellen** Menü die Option **Projektmappe** (oder drücken Sie **STRG**+**UMSCHALT** + **B**).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Fügen Sie Code zum Implementieren des WCF-Dienstvertrags.
> - Erstellen Sie die Projektmappe.

Fahren Sie fort mit dem nächsten Tutorial erfahren, wie den WCF-Dienst ausgeführt werden soll.

> [!div class="nextstepaction"]
> [Tutorial: Hosten und Ausführen eines grundlegenden WCF-Diensts](how-to-host-and-run-a-basic-wcf-service.md)
