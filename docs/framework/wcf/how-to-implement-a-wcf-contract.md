---
title: 'Tutorial: Implementieren eines Windows Communication Foundation Service-Vertrags'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 05923dc0a2223da5e5fcda483abc1ee1dd2d643f
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928708"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Tutorial: Implementieren eines Windows Communication Foundation Service-Vertrags

In diesem Tutorial wird die zweite von fünf Aufgaben beschrieben, die zum Erstellen einer Basic Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Tutorials finden [Sie unter Tutorial: Beginnen Sie mit Windows Communication Foundation Anwendungen](getting-started-tutorial.md).

Der nächste Schritt zum Erstellen einer WCF-Anwendung besteht darin, Code zum Implementieren der WCF-Dienst Schnittstelle hinzuzufügen, die Sie im vorherigen Schritt erstellt haben. In diesem Schritt erstellen Sie eine Klasse mit dem `CalculatorService` Namen, die die benutzerdefinierte `ICalculator` Schnittstelle implementiert. Jede Methode im folgenden Code Ruft einen Rechner Vorgang auf und schreibt Text in die Konsole, um Sie zu testen. 

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Fügen Sie Code hinzu, um den WCF-Dienstvertrag zu implementieren.
> - Erstellen Sie die Projektmappe.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Hinzufügen von Code zum Implementieren des WCF-Dienstvertrags

Öffnen Sie in **gettingstartedlib**die Datei **Service1.cs** oder **Service1. vb** , und ersetzen Sie den Code durch den folgenden Code:

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

## <a name="edit-appconfig"></a>Bearbeiten von "App. config"

Bearbeiten Sie die Datei **app. config** in **gettingstartedlib** , um die Änderungen widerzuspiegeln, die Sie am Code vorgenommen haben.

- Für visuelle C# Projekte:
  - Ändern Sie Zeile 14 in`<service name="GettingStartedLib.CalculatorService">`
  - Ändern Sie Zeile 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Ändern Sie Zeile 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Für Visual Basic-Projekte:
  - Ändern Sie Zeile 14 in`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Ändern Sie Zeile 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Ändern Sie Zeile 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Kompilieren des Codes

Erstellen Sie die Lösung, um sicherzustellen, dass keine Kompilierungsfehler vorliegen. Wenn Sie Visual Studio verwenden, wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** (oder drücken Sie **STRG**+**UMSCHALT**+**B**).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Fügen Sie Code hinzu, um den WCF-Dienstvertrag zu implementieren.
> - Erstellen Sie die Projektmappe.

Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den WCF-Dienst ausführen.

> [!div class="nextstepaction"]
> [Tutorial: Hosten und Ausführen eines einfachen WCF-Diensts](how-to-host-and-run-a-basic-wcf-service.md)
