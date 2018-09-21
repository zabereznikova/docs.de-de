---
title: 'Gewusst wie: Implementieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 569de6f49b56b46ccfeb22e9f0bd25bcf339b7e0
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46493202"
---
# <a name="how-to-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="0d1e7-102">Gewusst wie: Implementieren eines Windows Communication Foundation-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="0d1e7-102">How to: Implement a Windows Communication Foundation Service Contract</span></span>

<span data-ttu-id="0d1e7-103">Dies ist die zweite von sechs Aufgaben, die zum Erstellen eines grundlegenden Windows Communication Foundation (WCF)-Diensts und ein Client, der den Dienst aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="0d1e7-103">This is the second of six tasks required to create a basic Windows Communication Foundation (WCF) service and a client that can call the service.</span></span> <span data-ttu-id="0d1e7-104">Eine Übersicht über alle sechs Aufgaben, finden Sie unter den [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="0d1e7-104">For an overview of all six tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="0d1e7-105">Im nächsten Schritt zum Erstellen einer WCF-Anwendung wird die Dienstschnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="0d1e7-105">The next step in creating a WCF application is to implement the service interface.</span></span> <span data-ttu-id="0d1e7-106">Dies schließt die Erstellung einer `CalculatorService`-Klasse ein, die die benutzerdefinierte `ICalculator`-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="0d1e7-106">This involves creating a class called `CalculatorService` that implements the user-defined `ICalculator` interface..</span></span>

## <a name="to-implement-a-wcf-service-contract"></a><span data-ttu-id="0d1e7-107">So implementieren Sie einen WCF-Dienstvertrag</span><span class="sxs-lookup"><span data-stu-id="0d1e7-107">To implement a WCF service contract</span></span>

<span data-ttu-id="0d1e7-108">Öffnen Sie die Datei Service1.cs oder Service1.vb, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="0d1e7-108">Open the Service1.cs or Service1.vb file and add the following code:</span></span>

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

<span data-ttu-id="0d1e7-109">Jede Methode implementiert den Rechnervorgang und schreibt eine kleine Menge Text in die Konsole, um die Tests zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="0d1e7-109">Each method implements the calculator operation and writes some text to the console to make testing easier.</span></span>

## <a name="example"></a><span data-ttu-id="0d1e7-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d1e7-110">Example</span></span>

<span data-ttu-id="0d1e7-111">Im folgenden Code wird die Schnittstelle, die den Dienstvertrag definiert, sowie die Implementierung der Schnittstelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0d1e7-111">The following code shows both the interface that defines the contract and the implementation of the interface.</span></span>

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
    public interface ICalculator
    {
        [OperationContract]
        double Add(double n1, double n2);
        [OperationContract]
        double Subtract(double n1, double n2);
        [OperationContract]
        double Multiply(double n1, double n2);
        [OperationContract]
        double Divide(double n1, double n2);
    }
}
```

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

    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
    Public Interface ICalculator

        <OperationContract()> _
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
End Namespace
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

## <a name="compile-the-code"></a><span data-ttu-id="0d1e7-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0d1e7-112">Compile the code</span></span>

<span data-ttu-id="0d1e7-113">Erstellen Sie die Projektmappe aus, um sicherzustellen, dass keine Kompilierungsfehler vorliegen.</span><span class="sxs-lookup"><span data-stu-id="0d1e7-113">Build the solution to ensure there are no compilation errors.</span></span> <span data-ttu-id="0d1e7-114">Wenn Sie Visual Studio verwenden, sind die **erstellen** Menü die Option **Projektmappe** (oder drücken Sie **STRG**+**UMSCHALT** + **B**).</span><span class="sxs-lookup"><span data-stu-id="0d1e7-114">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0d1e7-115">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0d1e7-115">Next steps</span></span>

<span data-ttu-id="0d1e7-116">Der Dienstvertrag ist nun erstellt und implementiert.</span><span class="sxs-lookup"><span data-stu-id="0d1e7-116">Now the service contract is created and implemented.</span></span> <span data-ttu-id="0d1e7-117">Im nächsten Schritt führen Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="0d1e7-117">In the next step, you run the service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0d1e7-118">Vorgehensweise: Hosten und Ausführen eines grundlegenden Diensts</span><span class="sxs-lookup"><span data-stu-id="0d1e7-118">How to: Host and Run a Basic Service</span></span>](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)

<span data-ttu-id="0d1e7-119">Informationen zur Problembehandlung finden Sie unter [Troubleshooting the Getting Started Tutorial (Problembehandlung für das Tutorial „Erste Schritte“)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="0d1e7-119">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0d1e7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d1e7-120">See also</span></span>

- [<span data-ttu-id="0d1e7-121">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="0d1e7-121">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="0d1e7-122">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="0d1e7-122">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)