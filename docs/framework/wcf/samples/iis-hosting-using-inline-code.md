---
title: IIS-Hosting mithilfe von Inlinecode
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 47d056e35b92654c8e47647c7273c5d69b37bd97
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594646"
---
# <a name="iis-hosting-using-inline-code"></a><span data-ttu-id="7fefc-102">IIS-Hosting mithilfe von Inlinecode</span><span class="sxs-lookup"><span data-stu-id="7fefc-102">IIS Hosting Using Inline Code</span></span>

<span data-ttu-id="7fefc-103">Dieses Beispiel zeigt, wie ein von IIS (Internet Information Services, Internetinformationsdienste) gehosteter Dienst implementiert wird, bei dem der Code sich inline in einer SVC-Datei befindet und bei Bedarf kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="7fefc-103">This sample demonstrates how to implement a service hosted by Internet Information Services (IIS), where the service code is contained in-line in a .svc file and is compiled on demand.</span></span> <span data-ttu-id="7fefc-104">Dienstcode kann auch direkt in Quellcodedateien, die sich im Verzeichnis \App_Code der Anwendung befinden, oder in einer unter \bin bereitgestellten Assembly implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="7fefc-104">Service code can also be implemented directly in source code files located in the application's \App_Code directory, or compiled into assembly deployed in \bin.</span></span> <span data-ttu-id="7fefc-105">Diese Techniken werden im vorliegenden Beispiel nicht veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7fefc-105">This sample does not demonstrate these techniques.</span></span>

> [!NOTE]
> <span data-ttu-id="7fefc-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="7fefc-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fefc-107">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="7fefc-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="7fefc-108">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7fefc-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="7fefc-109">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7fefc-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7fefc-110">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7fefc-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

<span data-ttu-id="7fefc-111">In diesem Beispiel wird ein typischer Dienst gezeigt, der einen Vertrag implementiert, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="7fefc-111">The sample demonstrates a typical service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="7fefc-112">Der Dienst wird in IIS gehostet, und der gesamte Dienstcode befindet sich in der Datei "Service.svc".</span><span class="sxs-lookup"><span data-stu-id="7fefc-112">The service is hosted in IIS and the service code is entirely contained in the Service.svc file.</span></span> <span data-ttu-id="7fefc-113">Der Dienst wird vom Host aktiviert und erst dann kompiliert, wenn die erste Nachricht an den Dienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="7fefc-113">The service is host-activated and compiled on-demand by the first message sent to the service.</span></span> <span data-ttu-id="7fefc-114">Eine Vorkompilierung ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7fefc-114">There is no pre-compilation necessary.</span></span> <span data-ttu-id="7fefc-115">Der Dienst implementiert einen `ICalculator`-Vertrag, wie im folgenden Code definiert:</span><span class="sxs-lookup"><span data-stu-id="7fefc-115">The service implements an `ICalculator` contract as defined in the following code:</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
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
```

<span data-ttu-id="7fefc-116">Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück.</span><span class="sxs-lookup"><span data-stu-id="7fefc-116">The service implementation calculates and returns the appropriate result.</span></span>

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="7fefc-117">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7fefc-117">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="7fefc-118">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7fefc-118">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7fefc-119">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="7fefc-119">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="7fefc-120">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="7fefc-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="7fefc-121">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7fefc-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="7fefc-122">Nachdem die Projekt Mappe erstellt wurde, führen Sie Setup. bat aus, um die Service Model Samples-Anwendung in IIS 7,0 einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7fefc-122">After the solution has been built, run setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="7fefc-123">Das Verzeichnis Service Model Samples sollte jetzt als IIS 7,0-Anwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7fefc-123">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="7fefc-124">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7fefc-124">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span> <span data-ttu-id="7fefc-125">Ein Beispiel zum Erstellen einer Client Anwendung, die diesen Dienst aufruft, finden Sie unter Gewusst [wie: Erstellen eines Clients](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="7fefc-125">For an example on how to create a client application that can call this service, see [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7fefc-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7fefc-126">See also</span></span>

- <span data-ttu-id="7fefc-127">[AppFabric-Hosting- und -Persistenzbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="7fefc-127">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
