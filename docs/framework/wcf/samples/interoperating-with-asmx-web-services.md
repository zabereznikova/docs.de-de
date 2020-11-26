---
title: Zusammenwirken mit ASMX-Webdiensten
ms.date: 03/30/2017
ms.assetid: a7c11f0a-9e68-4f03-a6b1-39cf478d1a89
ms.openlocfilehash: 5e1a84d6dc70a26dd91f9ddce644c69689019690
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237676"
---
# <a name="interoperating-with-asmx-web-services"></a><span data-ttu-id="3dd29-102">Zusammenwirken mit ASMX-Webdiensten</span><span class="sxs-lookup"><span data-stu-id="3dd29-102">Interoperating with ASMX Web Services</span></span>

<span data-ttu-id="3dd29-103">In diesem Beispiel wird veranschaulicht, wie eine Windows Communication Foundation (WCF)-Client Anwendung in einen vorhandenen ASMX-Webdienst integriert wird.</span><span class="sxs-lookup"><span data-stu-id="3dd29-103">This sample demonstrates how to integrate a Windows Communication Foundation (WCF) client application with an existing ASMX Web service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3dd29-104">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="3dd29-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3dd29-105">Dieses Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek (.dll).</span><span class="sxs-lookup"><span data-stu-id="3dd29-105">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="3dd29-106">Bei dem Dienst handelt es sich um einen ASMX-Webdienst, der einen Vertrag implementiert, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="3dd29-106">The service is an ASMX Web Service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="3dd29-107">Der Dienst macht mathematische Operationen (`Add`, `Subtract`, `Multiply` und `Divide`) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3dd29-107">The service exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="3dd29-108">Der Client stellt synchrone Anforderungen an einen mathematischen Vorgang, und der Dienst antwortet mit dem Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="3dd29-108">The client makes synchronous requests to a math operation and the service replies with the result.</span></span> <span data-ttu-id="3dd29-109">Die Clientaktivität ist im Konsolenfenster sichtbar.</span><span class="sxs-lookup"><span data-stu-id="3dd29-109">Client activity is visible in the console window.</span></span>  
  
 <span data-ttu-id="3dd29-110">Die im folgenden Beispielcode dargestellte ASMX-Webdienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück.</span><span class="sxs-lookup"><span data-stu-id="3dd29-110">The ASMX Web service implementation shown in the following sample code calculates and returns the appropriate result.</span></span>  
  
```csharp  
[WebService(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class CalculatorService : System.Web.Services.WebService  
    {  
        [WebMethod]  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
        [WebMethod]  
        public double Subtract(double n1, double n2)  
        {  
            return n1 - n2;  
        }  
        [WebMethod]  
        public double Multiply(double n1, double n2)  
        {  
            return n1 * n2;  
        }  
        [WebMethod]  
        public double Divide(double n1, double n2)  
        {  
            return n1 / n2;  
        }  
    }  
```  
  
 <span data-ttu-id="3dd29-111">Wie konfiguriert, kann auf den Dienst `http://localhost/servicemodelsamples/service.asmx` von einem Client auf dem gleichen Computer zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="3dd29-111">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.asmx` by a client on the same machine.</span></span> <span data-ttu-id="3dd29-112">Für Clients auf Remotecomputern muss für den Dienstzugriff statt localhost ein vollqualifizierter Domänenname angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3dd29-112">For clients on remote machines to access the service, a qualified domain name must be specified instead of localhost.</span></span>  
  
 <span data-ttu-id="3dd29-113">Die Kommunikation erfolgt über einen Client, der durch das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)generiert wird.</span><span class="sxs-lookup"><span data-stu-id="3dd29-113">Communication is done through a client generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="3dd29-114">Der Client ist in der Datei "generatedClient.cs" enthalten.</span><span class="sxs-lookup"><span data-stu-id="3dd29-114">The client is contained in the file generatedClient.cs.</span></span> <span data-ttu-id="3dd29-115">Der ASMX-Dienst muss zur Generierung des Proxycodes verfügbar sein, da dieser zum Abrufen der aktualisierten Metadaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3dd29-115">The ASMX service must be available to generate the proxy code, because it is used to retrieve the updated metadata.</span></span> <span data-ttu-id="3dd29-116">Führen Sie den folgenden Befehl an einer Eingabeaufforderung im Clientverzeichnis aus, um den typisierten Proxy zu generieren.</span><span class="sxs-lookup"><span data-stu-id="3dd29-116">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedClient.cs  
```  
  
 <span data-ttu-id="3dd29-117">Durch das Verwenden des generierten Clients können Sie auf einen Dienstendpunkt zugreifen, indem Sie die entsprechende Adresse und Bindung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3dd29-117">By using the generated client, you can access a service endpoint by configuring the appropriate address and binding.</span></span> <span data-ttu-id="3dd29-118">Wie auch der Dienst gibt der Client den Endpunkt, mit dem er kommuniziert, mithilfe einer Konfigurationsdatei (App.config) an.</span><span class="sxs-lookup"><span data-stu-id="3dd29-118">Like the service, the client uses a configuration file (App.config) to specify the endpoint to communicate with.</span></span> <span data-ttu-id="3dd29-119">Die Clientendpunktkonfiguration besteht aus einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3dd29-119">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract, as shown in the following sample configuration.</span></span>  
  
```xml  
<client>  
   <endpoint
      address="http://localhost/ServiceModelSamples/service.asmx"
      binding="basicHttpBinding"
      contract="Microsoft.ServiceModel.Samples.CalculatorServiceSoap" />  
</client>  
```  
  
 <span data-ttu-id="3dd29-120">Die Clientimplementierung erstellt eine Instanz des generierten Clients.</span><span class="sxs-lookup"><span data-stu-id="3dd29-120">The client implementation constructs an instance of the generated client.</span></span> <span data-ttu-id="3dd29-121">Der generierte Client kann dann für die Kommunikation mit dem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3dd29-121">The generated client can then be used to communicate with the service.</span></span>  
  
```csharp  
// Create a client.  
CalculatorServiceSoapClient client = new CalculatorServiceSoapClient();  
  
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
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="3dd29-122">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3dd29-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="3dd29-123">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="3dd29-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3dd29-124">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="3dd29-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3dd29-125">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="3dd29-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="3dd29-126">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="3dd29-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="3dd29-127">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3dd29-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3dd29-128">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="3dd29-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3dd29-129">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3dd29-129">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3dd29-130">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3dd29-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3dd29-131">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="3dd29-131">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\Interop\ASMX`  
