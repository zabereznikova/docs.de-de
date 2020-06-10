---
title: Grundlegender Datenvertrag
ms.date: 03/30/2017
helpviewer_keywords:
- Data Contract
ms.assetid: b124e9e0-cb73-4ae0-b9c3-e6cdf5eced98
ms.openlocfilehash: 66df6a1d7c2df17e79925490644891c0a536b1cd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585492"
---
# <a name="basic-data-contract"></a><span data-ttu-id="94814-102">Grundlegender Datenvertrag</span><span class="sxs-lookup"><span data-stu-id="94814-102">Basic Data Contract</span></span>

<span data-ttu-id="94814-103">In diesem Beispiel wird das Implementieren eines Datenvertrags veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="94814-103">This sample demonstrates how to implement a data contract.</span></span> <span data-ttu-id="94814-104">Datenverträge ermöglichen es Ihnen, strukturierte Daten an Dienste zu übergeben und von ihnen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="94814-104">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="94814-105">Dieses Beispiel basiert [auf den ersten](getting-started-sample.md) Schritten, verwendet jedoch komplexe Zahlen anstelle von einfachen numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="94814-105">This sample is based on the [Getting Started](getting-started-sample.md) but uses complex numbers instead of basic numeric types.</span></span>

<span data-ttu-id="94814-106">In diesem Beispiel wird der Dienst von Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).</span><span class="sxs-lookup"><span data-stu-id="94814-106">In this sample, the service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>

> [!NOTE]
> <span data-ttu-id="94814-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="94814-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="94814-108">Der Dienstvertrag für diesen Dienst verwendet komplexe Zahlen, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="94814-108">The service contract for this service uses complex numbers, as shown in the following sample code.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    ComplexNumber Add(ComplexNumber n1, ComplexNumber n2);
    [OperationContract]
    ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2);
    [OperationContract]
    ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2);
    [OperationContract]
    ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2);
}
```

 <span data-ttu-id="94814-109">Das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut wurden auf die Definition der `ComplexNumber`-Klasse angewendet, um anzugeben, welche Felder der Klasse zwischen dem Client und dem Dienst übertragen werden können, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="94814-109">The <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes have been applied to the definition of the `ComplexNumber` class to indicate which fields of the class can be passed over the wire between the client and the service, as shown in the following sample code.</span></span>

```csharp
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public class ComplexNumber
{
    [DataMember]
    public double Real = 0.0D;
    [DataMember]
    public double Imaginary = 0.0D;

    public ComplexNumber(double real, double imaginary)
    {
        this.Real = real;
        this.Imaginary = imaginary;
    }
}
```

<span data-ttu-id="94814-110">Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück. Dabei werden Zahlen vom Typ `ComplexNumber` akzeptiert und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="94814-110">The service implementation calculates and returns the appropriate result, accepting and returning numbers of the `ComplexNumber` type.</span></span>

```csharp
// This is the service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)
    {
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +
                                                      n2.Imaginary);
    }

    public ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2)
    {
        return new ComplexNumber(n1.Real - n2.Real, n1.Imaginary -
                                                     n2.Imaginary);
    }
    public ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2)
    {
        double real1 = n1.Real * n2.Real;
        double imaginary1 = n1.Real * n2.Imaginary;
        double imaginary2 = n2.Real * n1.Imaginary;
        double real2 = n1.Imaginary * n2.Imaginary * -1;
        return new ComplexNumber(real1 + real2, imaginary1 +
                                                 imaginary2);
    }

    public ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2)
    {
         ComplexNumber conjugate =
              new ComplexNumber(n2.Real, -1*n2.Imaginary);
         ComplexNumber numerator = Multiply(n1, conjugate);
         ComplexNumber denominator = Multiply(n2, conjugate);
         return new ComplexNumber(numerator.Real / denominator.Real,
                                               numerator.Imaginary);
    }
}
```

<span data-ttu-id="94814-111">Die Clientimplementierung verwendet ebenfalls komplexe Zahlen.</span><span class="sxs-lookup"><span data-stu-id="94814-111">The client implementation also uses complex numbers.</span></span> <span data-ttu-id="94814-112">Sowohl der Dienstvertrag als auch der Datenvertrag werden in der Quelldatei generatedClient.cs definiert, die vom Service [Model Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) aus den Dienst Metadaten generiert wird.</span><span class="sxs-lookup"><span data-stu-id="94814-112">Both the service contract and the data contract are defined in the source file generatedClient.cs, which is generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) from service metadata.</span></span>

```csharp
// Create a client.
DataContractCalculatorClient client = new DataContractCalculatorClient();
// Call the Add service operation.
ComplexNumber value1 = new ComplexNumber()
                    {
                        Real = 1,
                        Imaginary = 2
                    };
ComplexNumber value2 = new ComplexNumber()
                    {
                        Real = 3,
                        Imaginary = 4
                    };
ComplexNumber result = proxy.Add(value1, value2);
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",
      value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,
      result.Real, result.Imaginary);
    …
}
```

<span data-ttu-id="94814-113">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten des Vorgangs im Konsolenfenster des Clients angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94814-113">When you run the sample, the requests and responses of the operation are displayed in the client console window.</span></span> <span data-ttu-id="94814-114">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="94814-114">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(1 + 2i, 3 + 4i) = 4 + 6i
Subtract(1 + 2i, 3 + 4i) = -2 + -2i
Multiply(2 + 3i, 4 + 7i) = -13 + 26i
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 41i

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="94814-115">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="94814-115">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="94814-116">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="94814-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="94814-117">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="94814-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="94814-118">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="94814-118">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94814-119">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="94814-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="94814-120">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="94814-120">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="94814-121">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94814-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="94814-122">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="94814-122">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\Basic`
