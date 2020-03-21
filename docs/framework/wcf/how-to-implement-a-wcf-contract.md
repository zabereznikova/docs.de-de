---
title: 'Tutorial: Implementieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: debdeeac7064f5bae21622b2d9de84a4d8a0e66f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184070"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Tutorial: Implementieren eines Windows Communication Foundation-Dienstvertrags

In diesem Tutorial wird die zweite von fünf Aufgaben beschrieben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).

Der nächste Schritt zum Erstellen einer WCF-Anwendung besteht darin, Code hinzuzufügen, um die WCF-Dienstschnittstelle zu implementieren, die Sie im vorherigen Schritt erstellt haben. In diesem Schritt erstellen Sie `CalculatorService` eine Klasse mit `ICalculator` dem Namen, die die benutzerdefinierte Schnittstelle implementiert. Jede Methode im folgenden Code ruft einen Rechnervorgang auf und schreibt Text in die Konsole, um ihn zu testen.

In diesem Tutorial lernen Sie Folgendes:
> [!div class="checklist"]
>
> - Fügen Sie Code hinzu, um den WCF-Servicevertrag zu implementieren.
> - Erstellen Sie die Projektmappe.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Hinzufügen von Code zum Implementieren des WCF-Servicevertrags

Öffnen Sie unter **GettingStartedLib**die **Datei Service1.cs** oder **Service1.vb,** und ersetzen Sie ihren Code durch den folgenden Code:

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

## <a name="edit-appconfig"></a>App.config bearbeiten

Bearbeiten Sie **App.config** in **GettingStartedLib,** um die Änderungen widerzuspiegeln, die Sie am Code vorgenommen haben.

- Für Visual C-Projekte:
  - Änderung der Zeile 14 in`<service name="GettingStartedLib.CalculatorService">`
  - Änderung der Zeile 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Änderung der Zeile 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Für Visual Basic-Projekte:
  - Änderung der Zeile 14 in`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Änderung der Zeile 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Änderung der Zeile 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Kompilieren des Codes

Erstellen Sie die Lösung, um sicherzustellen, dass keine Kompilierungsfehler vorliegen. Wenn Sie Visual Studio verwenden, wählen Sie im Menü **Erstellen** **die Option Lösung erstellen** aus (oder drücken Sie **Strg**+**um Schicht**+**B**).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Folgendes gelernt:
> [!div class="checklist"]
>
> - Fügen Sie Code hinzu, um den WCF-Servicevertrag zu implementieren.
> - Erstellen Sie die Projektmappe.

Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den WCF-Dienst ausführen.

> [!div class="nextstepaction"]
> [Tutorial: Hosten und Ausführen eines grundlegenden WCF-Dienstes](how-to-host-and-run-a-basic-wcf-service.md)
