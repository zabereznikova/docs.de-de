---
title: Standardnachrichtenvertrag
ms.date: 03/30/2017
helpviewer_keywords:
- Message Contract
ms.assetid: 5a200b78-1a46-4104-b7fb-da6dbab33893
ms.openlocfilehash: 46b69697616ad7983daed16f8a180a4da7f61a16
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183768"
---
# <a name="default-message-contract"></a><span data-ttu-id="ea24d-102">Standardnachrichtenvertrag</span><span class="sxs-lookup"><span data-stu-id="ea24d-102">Default Message Contract</span></span>
<span data-ttu-id="ea24d-103">Das Beispiel zum Standardnachrichtenvertrag zeigt einen Dienst, bei dem eine benutzerdefinierte Nachricht an und aus Dienstvorgängen übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ea24d-103">The Default Message Contract sample demonstrates a service where a custom user-defined message is passed to and from service operations.</span></span> <span data-ttu-id="ea24d-104">Dieses Beispiel basiert auf dem [Ersten Schritte,](../../../../docs/framework/wcf/samples/getting-started-sample.md) das eine Rechnerschnittstelle als typisierten Dienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="ea24d-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator interface as a typed service.</span></span> <span data-ttu-id="ea24d-105">Anstelle der einzelnen Dienstvorgänge für Addition, Subtraktion, Multiplikation und Division, [die](../../../../docs/framework/wcf/samples/getting-started-sample.md)in den Vorgängen verwendet werden, übergibt dieses Beispiel eine benutzerdefinierte Nachricht, die sowohl die Operanden als auch den Operator enthält, und gibt das Ergebnis der arithmetischen Berechnung zurück.</span><span class="sxs-lookup"><span data-stu-id="ea24d-105">Instead of the individual service operations for addition, subtraction, multiplication, and division used in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), this sample passes a custom message that contains both the operands and the operator, and returns the result of the arithmetic calculation.</span></span>  
  
 <span data-ttu-id="ea24d-106">Der Client ist ein Konsolenprogramm (.exe), und die Dienstbibliothek (.dll) wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="ea24d-106">The client is a console program (.exe) and the service library (.dll) is hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="ea24d-107">Die Clientaktivität ist im Konsolenfenster sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ea24d-107">Client activity is visible in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea24d-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="ea24d-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ea24d-109">In dem Dienst ist ein Dienstvorgang definiert, der benutzerdefinierte Nachrichten vom Typ `MyMessage` entgegennimmt und zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ea24d-109">In the service, a single service operation is defined that accepts and returns custom messages of type `MyMessage`.</span></span> <span data-ttu-id="ea24d-110">Auch wenn im vorliegenden Beispiel die Anforderung- und Antwortnachrichten vom selben Typ sind, können sie natürlich auch unterschiedliche Nachrichtenverträge sein, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ea24d-110">Although in this sample the request and response messages are of the same type, they could of course be different message contracts if necessary.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract(Action="http://test/MyMessage_action",  
                  ReplyAction="http://test/MyMessage_action")]  
    MyMessage Calculate(MyMessage request);  
}  
```  
  
 <span data-ttu-id="ea24d-111">Die benutzerdefinierte `MyMessage`-Nachricht wird in einer mit <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>- und <xref:System.ServiceModel.MessageBodyMemberAttribute>-Attributen kommentierten Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="ea24d-111">The custom message `MyMessage` is defined in a class annotated with <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes.</span></span> <span data-ttu-id="ea24d-112">In diesem Beispiel wird nur der dritte Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea24d-112">Only the third constructor is used in this sample.</span></span> <span data-ttu-id="ea24d-113">Mithilfe von Nachrichtenverträgen können Sie die volle Kontrolle über die SOAP-Nachricht ausüben.</span><span class="sxs-lookup"><span data-stu-id="ea24d-113">Using message contracts allows you to exercise full control over the SOAP message.</span></span> <span data-ttu-id="ea24d-114">In diesem Beispiel wird mit dem <xref:System.ServiceModel.MessageHeaderAttribute>-Attribut `Operation` in einem SOAP-Header platziert.</span><span class="sxs-lookup"><span data-stu-id="ea24d-114">In this sample, the <xref:System.ServiceModel.MessageHeaderAttribute> attribute is used to put `Operation` in a SOAP header.</span></span> <span data-ttu-id="ea24d-115">Die Operanden `N1` und `N2` sowie das `Result` werden im SOAP-Text angezeigt, da auf sie das <xref:System.ServiceModel.MessageBodyMemberAttribute>-Attribut angewendet ist.</span><span class="sxs-lookup"><span data-stu-id="ea24d-115">The operands `N1`, `N2` and the `Result` appear within the SOAP body because they have the <xref:System.ServiceModel.MessageBodyMemberAttribute> attribute applied.</span></span>  
  
```csharp
[MessageContract]  
public class MyMessage  
{  
    private string operation;  
    private double n1;  
    private double n2;  
    private double result;  
  
    //Constructor - create an empty message.  
  
    public MyMessage() {}  
  
    //Constructor - create a message and populate its members.  
  
    public MyMessage(double n1, double n2, string operation,
                     double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    //Constructor - create a message from another message.  
  
    public MyMessage(MyMessage message)  
    {  
        this.n1 = message.n1;  
        this.n2 = message.n2;  
        this.operation = message.operation;  
        this.result = message.result;  
    }  
  
    [MessageHeader]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [MessageBodyMember]  
    public double N1  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [MessageBodyMember]  
    public double N2  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [MessageBodyMember]  
    public double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
}  
```  
  
 <span data-ttu-id="ea24d-116">Die Implementierungsklasse enthält den Code für den `Calculate`-Dienstvorgang.</span><span class="sxs-lookup"><span data-stu-id="ea24d-116">The implementation class contains the code for the `Calculate` service operation.</span></span> <span data-ttu-id="ea24d-117">Die `CalculateService`-Klasse ermittelt die Operanden und den Operator aus der Anforderungsnachricht und erstellt eine Antwortnachricht, die das Ergebnis der angeforderten Berechnung enthält, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ea24d-117">The `CalculateService` class obtains the operands and operator from the request message and creates a response message that contains the result of the requested calculation, as shown in the following sample code.</span></span>  
  
```csharp
// Service class which implements the service contract.  
public class CalculatorService : ICalculator  
{  
    // Perform a calculation.  
  
    public MyMessage Calculate(MyMessage request)  
    {  
        MyMessage response = new MyMessage(request);  
        switch (request.Operation)  
        {  
            case "+":  
                response.Result = request.N1 + request.N2;  
                break;  
            case "-":  
                response.Result = request.N1 - request.N2;  
                break;  
            case "*":  
                response.Result = request.N1 * request.N2;  
                break;  
            case "/":  
                response.Result = request.N1 / request.N2;  
                break;  
            default:  
                response.Result = 0.0D;  
                break;  
        }  
        return response;  
    }  
}  
```  
  
 <span data-ttu-id="ea24d-118">Der generierte Clientcode für den Client wurde mit dem [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) erstellt.</span><span class="sxs-lookup"><span data-stu-id="ea24d-118">The generated client code for the client was created with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool.</span></span> <span data-ttu-id="ea24d-119">Wenn erforderlich, erstellt das Tool automatisch Nachrichtenvertragstypen im generierten Clientcode.</span><span class="sxs-lookup"><span data-stu-id="ea24d-119">The tool automatically creates message contract types in the generated client code if necessary.</span></span> <span data-ttu-id="ea24d-120">Die `/messageContract`-Befehlsoption kann angegeben werden, um die Generierung von Nachrichtenverträgen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ea24d-120">The `/messageContract` command option may be specified to force the generation of message contracts.</span></span>  
  
```console  
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" /o:client\generatedClient.cs http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="ea24d-121">Das folgende Codebeispiel zeigt den Client mit der `MyMessage`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="ea24d-121">The following sample code demonstrates the client using the `MyMessage` message.</span></span>  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
// Perform addition using a typed message.  
  
MyMessage request = new MyMessage()
                    {  
                        N1 = 100D,  
                        N2 = 15.99D,  
                        Operation = "+"  
                    };
MyMessage response = ((ICalculator)client).Calculate(request);  
Console.WriteLine("Add({0},{1}) = {2}", request.N1, request.N2, response.Result);  
```  
  
 <span data-ttu-id="ea24d-122">Wenn Sie das Beispiel ausführen, werden die Berechnungen im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea24d-122">When you run the sample, the calculations are displayed in the client console window.</span></span> <span data-ttu-id="ea24d-123">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ea24d-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="ea24d-124">An dieser Stelle wurden benutzerdefinierte Nachrichten zwischen dem Client und dem Dienstvorgang übergeben.</span><span class="sxs-lookup"><span data-stu-id="ea24d-124">At this point, custom user-defined messages have passed between the client and the service operation.</span></span> <span data-ttu-id="ea24d-125">Der Nachrichtenvertrag hat definiert, dass sich die Operanden und Ergebnisse im Nachrichtentextteil und der Operator in einem Nachrichtenheader befinden.</span><span class="sxs-lookup"><span data-stu-id="ea24d-125">The message contract defined that the operands and results were in the message body and that the operator was in a message header.</span></span> <span data-ttu-id="ea24d-126">Zum Betrachten dieser Nachrichtenstruktur kann Nachrichtenprotokollierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ea24d-126">Message logging can be configured to observe this message structure.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ea24d-127">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="ea24d-127">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ea24d-128">Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="ea24d-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ea24d-129">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ea24d-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ea24d-130">Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ea24d-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ea24d-131">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ea24d-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ea24d-132">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ea24d-132">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ea24d-133">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ea24d-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ea24d-134">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ea24d-134">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Default`  
