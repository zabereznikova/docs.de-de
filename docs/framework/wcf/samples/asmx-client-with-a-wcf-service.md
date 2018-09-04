---
title: ASMX-Client mit einem WCF-Dienst
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: 3465954cc937e1611634c8cd13a9264173e71817
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507198"
---
# <a name="asmx-client-with-a-wcf-service"></a><span data-ttu-id="60fe1-102">ASMX-Client mit einem WCF-Dienst</span><span class="sxs-lookup"><span data-stu-id="60fe1-102">ASMX Client with a WCF Service</span></span>
<span data-ttu-id="60fe1-103">Dieses Beispiel veranschaulicht das Erstellen eines Diensts mithilfe von Windows Communication Foundation (WCF), und klicken Sie dann auf den Dienst zugreifen, von einem nicht-WCF-Client, z. B. eine ASMX-Client.</span><span class="sxs-lookup"><span data-stu-id="60fe1-103">This sample demonstrates how to create a service using Windows Communication Foundation (WCF) and then access the service from a non-WCF client, such as an ASMX client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60fe1-104">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="60fe1-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="60fe1-105">Dieses Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek (.dll).</span><span class="sxs-lookup"><span data-stu-id="60fe1-105">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="60fe1-106">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="60fe1-106">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="60fe1-107">Der Vertrag wird durch die `ICalculator`-Schnittstelle definiert, die mathematische Operationen (`Add`, `Subtract`, `Multiply` und `Divide`) verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="60fe1-107">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="60fe1-108">Der ASMX-Client stellt synchrone Anforderungen an eine mathematische Operation, und der Dienst antwortet mit dem Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="60fe1-108">The ASMX client makes synchronous requests to a math operation and the service replies with the result.</span></span>  
  
 <span data-ttu-id="60fe1-109">Der Dienst implementiert einen `ICalculator`-Vertrag, wie im folgenden Code definiert.</span><span class="sxs-lookup"><span data-stu-id="60fe1-109">The service implements an `ICalculator` contract as defined in the following code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
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
  
 <span data-ttu-id="60fe1-110"><xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Xml.Serialization.XmlSerializer> ordnen CLR-Typen einer XML-Darstellung zu.</span><span class="sxs-lookup"><span data-stu-id="60fe1-110">The <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Xml.Serialization.XmlSerializer> map CLR types to an XML representation.</span></span> <span data-ttu-id="60fe1-111">Der <xref:System.Runtime.Serialization.DataContractSerializer> übersetzt einige XML-Darstellungen anders als XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="60fe1-111">The <xref:System.Runtime.Serialization.DataContractSerializer> interprets some XML representations differently than XmlSerializer.</span></span> <span data-ttu-id="60fe1-112">Nicht-WCF-Proxy-Generatoren wie Wsdl.exe, generieren eine Schnittstelle, wenn das XmlSerializer-Element verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="60fe1-112">Non-WCF proxy generators, such as Wsdl.exe, generate a more usable interface when the XmlSerializer is being used.</span></span> <span data-ttu-id="60fe1-113">Die <xref:System.ServiceModel.XmlSerializerFormatAttribute> gilt, an die `ICalculator` -Schnittstelle, um sicherzustellen, dass das XmlSerializer-Element zum Zuordnen von CLR-Typen zu XML verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="60fe1-113">The <xref:System.ServiceModel.XmlSerializerFormatAttribute> is applied to the `ICalculator` interface, to ensure that the XmlSerializer is used for mapping CLR types to XML.</span></span> <span data-ttu-id="60fe1-114">Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück.</span><span class="sxs-lookup"><span data-stu-id="60fe1-114">The service implementation calculates and returns the appropriate result.</span></span>  
  
 <span data-ttu-id="60fe1-115">Der Dienst macht einen einzigen Endpunkt zur Kommunikation mit dem Dienst verfügbar, der mit einer Konfigurationsdatei (Web.conf) definiert wird.</span><span class="sxs-lookup"><span data-stu-id="60fe1-115">The service exposes a single endpoint for communicating with the service, defined using a configuration file (Web.config).</span></span> <span data-ttu-id="60fe1-116">Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="60fe1-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="60fe1-117">Der Dienst macht den Endpunkt bei der vom IIS-Host bereitgestellten Basisadresse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="60fe1-117">The service exposes the endpoint at the base address provided by the Internet Information Services (IIS) host.</span></span> <span data-ttu-id="60fe1-118">Das `binding`-Attribut wird auf basicHttpBinding festgelegt, was die HTTP-Kommunikation über SOAP 1.1 ermöglicht, das mit WS-I BasicProfile 1.1 kompatibel ist, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="60fe1-118">The `binding` attribute is set to basicHttpBinding that provides HTTP communications using SOAP 1.1, which is compliant with WS-I BasicProfile 1.1 as shown in the following sample configuration.</span></span>  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->  
    <endpoint address=""  
              binding="basicHttpBinding"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </service>  
</services>  
```  
  
 <span data-ttu-id="60fe1-119">Der ASMX-Client kommuniziert mit den WCF-Dienst mittels eines typisierten Proxys, das vom Hilfsprogramm Web Services Description Language (WSDL) (Wsdl.exe) generiert wird.</span><span class="sxs-lookup"><span data-stu-id="60fe1-119">The ASMX client communicates with the WCF service using a typed proxy that is generated by the Web Services Description Language (WSDL) utility (Wsdl.exe).</span></span> <span data-ttu-id="60fe1-120">Der typisierte Proxy ist in der Datei generatedClient.cs enthalten.</span><span class="sxs-lookup"><span data-stu-id="60fe1-120">The typed proxy is contained in the file generatedClient.cs.</span></span> <span data-ttu-id="60fe1-121">Das WSDL-Dienstprogramm ruft Metadaten für den angegebenen Dienst ab und generiert einen typisierten Proxy, den ein Client zur Kommunikation verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="60fe1-121">The WSDL utility retrieves metadata for the specified service and generates a typed proxy for use by a client to communicate.</span></span> <span data-ttu-id="60fe1-122">Standardmäßig macht das Framework keine Metadaten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="60fe1-122">By default, the framework does not expose any metadata.</span></span> <span data-ttu-id="60fe1-123">Zum Verfügbarmachen von Metadaten erforderlich, um den Proxy zu generieren, müssen Sie hinzufügen, eine [ \<ServiceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) und legen Sie dessen `httpGetEnabled` Attribut `True` wie in der folgenden Konfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="60fe1-123">To expose the metadata required to generate the proxy, you must add a [\<serviceMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) and set its `httpGetEnabled` attribute to `True` as shown in the following configuration.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- Setting httpGetEnabled to True on the serviceMetadata  
           behavior exposes the service's wsdl at <base address>?wsdl :  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="60fe1-124">Führen Sie den folgenden Befehl an einer Eingabeaufforderung im Clientverzeichnis aus, um den typisierten Proxy zu generieren.</span><span class="sxs-lookup"><span data-stu-id="60fe1-124">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>  
  
```console  
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl  
```  
  
 <span data-ttu-id="60fe1-125">Unter Verwendung des generierten typisierten Proxys kann der Client auf einen bestimmten Endpunkt zugreifen, indem er die entsprechende Adresse konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="60fe1-125">By using the generated typed proxy, the client can access a given service endpoint by configuring the appropriate address.</span></span> <span data-ttu-id="60fe1-126">Der Client gibt den Endpunkt, mit dem er kommunizieren möchte, mithilfe einer Konfigurationsdatei (App.config) an.</span><span class="sxs-lookup"><span data-stu-id="60fe1-126">The client uses a configuration file (App.config) to specify the endpoint to communicate with.</span></span>  
  
```xml  
<appSettings>  
  <add key="CalculatorServiceAddress"   
       value="http://localhost/ServiceModelSamples/service.svc"/>  
</appSettings>  
```  
  
 <span data-ttu-id="60fe1-127">Die Clientimplementierung erstellt eine Instanz des typisierten Proxys, um die Kommunikation mit dem Dienst zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="60fe1-127">The client implementation constructs an instance of the typed proxy to begin communicating with the service.</span></span>  
  
```  
// Create a client to the CalculatorService.  
using (CalculatorService client = new CalculatorService())  
{  
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
  
}  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="60fe1-128">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60fe1-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="60fe1-129">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="60fe1-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="60fe1-130">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="60fe1-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="60fe1-131">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="60fe1-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="60fe1-132">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="60fe1-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="60fe1-133">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="60fe1-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60fe1-134">Weitere Informationen zu übergeben und Zurückgeben von komplexen Datentypen finden Sie unter: [Datenbindung in einem Windows Forms-Client](../../../../docs/framework/wcf/samples/data-binding-in-a-windows-forms-client.md), [Datenbindung in einem Windows Presentation Foundation-Client](../../../../docs/framework/wcf/samples/data-binding-in-a-wpf-client.md), und [Daten Datenbindung in einem ASP.NET-Client](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)</span><span class="sxs-lookup"><span data-stu-id="60fe1-134">For more information about passing and returning complex data types see: [Data Binding in a Windows Forms Client](../../../../docs/framework/wcf/samples/data-binding-in-a-windows-forms-client.md), [Data Binding in a Windows Presentation Foundation Client](../../../../docs/framework/wcf/samples/data-binding-in-a-wpf-client.md), and [Data Binding in an ASP.NET Client](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="60fe1-135">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="60fe1-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="60fe1-136">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="60fe1-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="60fe1-137">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="60fe1-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="60fe1-138">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="60fe1-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`  
  
## <a name="see-also"></a><span data-ttu-id="60fe1-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60fe1-139">See Also</span></span>
