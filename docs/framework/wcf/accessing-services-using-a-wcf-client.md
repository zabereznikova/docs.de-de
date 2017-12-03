---
title: Zugreifen auf Dienste mithilfe eines WCF-Clients
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d8698e0657de31d78699df478da5e716bf831fc4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="accessing-services-using-a-wcf-client"></a><span data-ttu-id="b0794-102">Zugreifen auf Dienste mithilfe eines WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="b0794-102">Accessing Services Using a WCF Client</span></span>
<span data-ttu-id="b0794-103">Nach dem Erstellen eines Diensts ist der nächste Schritt das Erstellen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientproxys.</span><span class="sxs-lookup"><span data-stu-id="b0794-103">After you create a service, the next step is to create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client proxy.</span></span> <span data-ttu-id="b0794-104">Eine Clientanwendung verwendet den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientproxy, um mit dem Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="b0794-104">A client application uses the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client proxy to communicate with the service.</span></span> <span data-ttu-id="b0794-105">Clientanwendungen importieren normalerweise Metadaten eines Dienstes zum Generieren von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientcode, mit dem der Dienst aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b0794-105">Client applications usually import a service's metadata to generate [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client code that can be used to invoke the service.</span></span>  
  
 <span data-ttu-id="b0794-106">Nachfolgend werden die grundlegenden Schritte zum Erstellen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clients aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="b0794-106">The basic steps for creating a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client include the following:</span></span>  
  
1.  <span data-ttu-id="b0794-107">Kompilieren Sie den Dienstcode.</span><span class="sxs-lookup"><span data-stu-id="b0794-107">Compile the service code.</span></span>  
  
2.  <span data-ttu-id="b0794-108">Generieren Sie den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientproxy.</span><span class="sxs-lookup"><span data-stu-id="b0794-108">Generate the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client proxy.</span></span>  
  
3.  <span data-ttu-id="b0794-109">Instanziieren Sie den WCF-Clientproxy.</span><span class="sxs-lookup"><span data-stu-id="b0794-109">Instantiate the WCF client proxy.</span></span>  
  
 <span data-ttu-id="b0794-110">Der WCF-Clientproxy kann manuell generiert werden, mithilfe der Service Model Metadata Utility Tool (SvcUtil.exe) Weitere Informationen finden Sie unter [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b0794-110">The WCF client proxy can be generated manually by using the Service Model Metadata Utility Tool (SvcUtil.exe) for more information see, [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="b0794-111">Der WCF-Clientproxy kann auch mithilfe der Funktion Dienstverweis hinzufügen in Visual Studio generiert werden.</span><span class="sxs-lookup"><span data-stu-id="b0794-111">The WCF client proxy can also be generated within Visual Studio using the Add Service Reference  feature.</span></span> <span data-ttu-id="b0794-112">Um den WCF-Clientproxy mithilfe einer dieser Methoden zu generieren, muss der Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b0794-112">To generate the WCF client proxy using either method the service must be running.</span></span> <span data-ttu-id="b0794-113">Wenn es sich um einen selbst gehosteten Dienst handelt, müssen Sie den Host ausführen.</span><span class="sxs-lookup"><span data-stu-id="b0794-113">If the service is self-hosted you must run the host.</span></span> <span data-ttu-id="b0794-114">Wenn der Dienst in IIS/WAS gehostet wird, ist kein weiterer Schritt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b0794-114">If the service is hosted in IIS/WAS you do not need to do anything else.</span></span>  
  
## <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="b0794-115">ServiceModel Metadata Utility Tool</span><span class="sxs-lookup"><span data-stu-id="b0794-115">ServiceModel Metadata Utility Tool</span></span>  
 <span data-ttu-id="b0794-116">Die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) ist ein Befehlszeilentool zum Generieren von Code aus den Metadaten.</span><span class="sxs-lookup"><span data-stu-id="b0794-116">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) is a command-line tool for generating code from metadata.</span></span> <span data-ttu-id="b0794-117">Die folgende Verwendung ist ein Beispiel für einen grundlegenden Svcutil.exe-Befehl.</span><span class="sxs-lookup"><span data-stu-id="b0794-117">The following use is an example of a basic Svcutil.exe command.</span></span>  
  
```  
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
```  
  
 <span data-ttu-id="b0794-118">Alternativ können Sie Svcutil.exe mit WSDL (Web Services Description Language) und XSD (XML Schema Definition Language)-Dateien im Dateisystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0794-118">Alternatively, you can use Svcutil.exe with Web Services Description Language (WSDL) and XML Schema definition language (XSD) files on the file system.</span></span>  
  
```  
Svcutil.exe <list of WSDL and XSD files on file system>  
```  
  
 <span data-ttu-id="b0794-119">Das Ergebnis ist ein Code, der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientcode enthält, mit dem die Clientanwendung den Dienst aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="b0794-119">The result is a code file that contains [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client code that the client application can use to invoke the service.</span></span>  
  
 <span data-ttu-id="b0794-120">Sie können das Tool auch zum Generieren von Konfigurationsdateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0794-120">You can also use the tool to generate configuration files.</span></span>  
  
```  
Svcutil.exe <file1 [,file2]>  
```  
  
 <span data-ttu-id="b0794-121">Wenn nur ein Dateiname angegeben wird, ist das der Name der Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="b0794-121">If only one file name is given, that is the name of the output file.</span></span> <span data-ttu-id="b0794-122">Wenn zwei Dateinamen angegeben werden, ist die erste Datei eine Eingabekonfigurationsdatei, deren Inhalt mit der generierten Konfiguration zusammengeführt und in die zweite Datei geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="b0794-122">If two file names are given, then the first file is an input configuration file whose contents are merged with the generated configuration and written out into the second file.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="b0794-123">Konfiguration finden Sie unter [Konfigurieren von Bindungen für Dienste](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b0794-123"> configuration, see [Configuring Bindings for Services](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b0794-124">Nicht gesicherte Metadatenanforderungen stellen genau wie nicht gesicherte Netzwerkanforderungen ein gewisses Risiko dar: Wenn Sie sich nicht sicher sind, ob der Endpunkt, mit dem Sie kommunizieren, der vorgegebenen Identität entspricht, stammen die abgerufenen Informationen unter Umständen von einem bösartigen Dienst.</span><span class="sxs-lookup"><span data-stu-id="b0794-124">Unsecured metadata requests pose certain risks in the same way that any unsecured network request does: If you are not certain that the endpoint you are communicating with is who it says it is, the information you retrieve might be metadata from a malicious service.</span></span>  
  
## <a name="add-service-reference-in-visual-studio"></a><span data-ttu-id="b0794-125">"Dienstverweis hinzufügen" in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0794-125">Add Service Reference in Visual Studio</span></span>  
 <span data-ttu-id="b0794-126">Mit dem Dienst wird ausgeführt, mit der rechten Maustaste klicken Sie auf das Projekt, das den WCF-Clientproxy enthalten wird, und wählen **Hinzufügen eines Dienstverweises**.</span><span class="sxs-lookup"><span data-stu-id="b0794-126">With the service running, right click the project that will contain the WCF client proxy and select **Add Service Reference**.</span></span> <span data-ttu-id="b0794-127">In der **hinzufügen "Dienstverweis"** Geben Sie die URL des Diensts, die Sie verwenden möchten, rufen Sie aus, und klicken Sie auf die **Go** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="b0794-127">In the **Add Service Reference Dialog** type in the URL to the service you want to call and click the **Go** button.</span></span> <span data-ttu-id="b0794-128">Das Dialogfeld zeigt eine Liste der Dienste an, die unter der Adresse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b0794-128">The dialog will display a list of services available at the address you specify.</span></span> <span data-ttu-id="b0794-129">Klicken Sie mit der Doppelklicken auf den Dienst finden Sie unter die Verträge und Vorgänge verfügbar, geben Sie einen Namespace für den generierten Code aus, und klicken Sie auf die **OK** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="b0794-129">Double click the service to see the contracts and operations available, specify a namespace for the generated code and click the **OK** button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0794-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0794-130">Example</span></span>  
 <span data-ttu-id="b0794-131">Im folgenden Codebeispiel wird ein für einen Dienst erstellter Dienstvertrag gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0794-131">The following code example shows a service contract created for a service.</span></span>  
  
```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```
  
```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```
  
 <span data-ttu-id="b0794-132">Das ServiceModel Metadata Utility-Tool und Dienstverweis hinzufügen[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] in Visual Studio generieren die folgende -Clientklasse.</span><span class="sxs-lookup"><span data-stu-id="b0794-132">The ServiceModel Metadata utility tool and Add Service Reference in Visual Studio generates the following [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client class.</span></span> <span data-ttu-id="b0794-133">Die Klasse erbt von der generischen <xref:System.ServiceModel.ClientBase%601>-Klasse und implementiert die `ICalculator`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b0794-133">The class inherits from the generic <xref:System.ServiceModel.ClientBase%601> class and implements the `ICalculator` interface.</span></span> <span data-ttu-id="b0794-134">Das Tool generiert auch die `ICalculator`-Schnittstelle (wird hier nicht gezeigt).</span><span class="sxs-lookup"><span data-stu-id="b0794-134">The tool also generates the `ICalculator` interface (not shown here).</span></span>  
  
```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```  
  
```vb  
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```
  
## <a name="using-the-wcf-client"></a><span data-ttu-id="b0794-135">Verwenden des WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="b0794-135">Using the WCF Client</span></span>  
 <span data-ttu-id="b0794-136">Erstellen Sie zum Verwenden des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clients eine Instanz des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clients, und rufen Sie dann seine Methoden auf, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0794-136">To use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client, create an instance of the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client, and then call its methods, as shown in the following code.</span></span>  
  
```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```
  
```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```
  
## <a name="debugging-exceptions-thrown-by-a-client"></a><span data-ttu-id="b0794-137">Debuggen der von einem Client ausgelösten Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="b0794-137">Debugging Exceptions Thrown by a Client</span></span>  
 <span data-ttu-id="b0794-138">Viele von einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Client ausgelöste Ausnahmen werden von einer Ausnahme des Diensts verursacht.</span><span class="sxs-lookup"><span data-stu-id="b0794-138">Many exceptions thrown by a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client are caused by an exception on the service.</span></span> <span data-ttu-id="b0794-139">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="b0794-139">Some examples of this are:</span></span>  
  
-   <span data-ttu-id="b0794-140"><xref:System.Net.Sockets.SocketException>: Vom Remotehost wurde die Schließung einer bestehenden Verbindung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="b0794-140"><xref:System.Net.Sockets.SocketException>: An existing connection was forcibly closed by the remote host.</span></span>  
  
-   <span data-ttu-id="b0794-141"><xref:System.ServiceModel.CommunicationException>: Die zugrunde liegende Verbindung wurde unerwartet geschlossen.</span><span class="sxs-lookup"><span data-stu-id="b0794-141"><xref:System.ServiceModel.CommunicationException>: The underlying connection was closed unexpectedly.</span></span>  
  
-   <span data-ttu-id="b0794-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: Die Socketverbindung wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="b0794-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: The socket connection was aborted.</span></span> <span data-ttu-id="b0794-143">Mögliche Ursache: Ein Fehler beim Verarbeiten der Nachricht, eine Zeitüberschreitung durch den Remotehost beim Empfang oder ein Problem mit einer zugrunde liegenden Netzwerkressource.</span><span class="sxs-lookup"><span data-stu-id="b0794-143">This could be caused by an error processing your message, a receive time-out being exceeded by the remote host, or an underlying network resource issue.</span></span>  
  
 <span data-ttu-id="b0794-144">Tritt eine Ausnahme dieses Typs auf, aktivieren Sie die Ablaufverfolgung auf der Dienstseite, und ermitteln Sie die dort aufgetretene Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="b0794-144">When these types of exceptions occur, the best way to solve the problem is to turn on tracing on the service side and determine what exception occurred there.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="b0794-145">Ablaufverfolgung, finden Sie unter [Ablaufverfolgung](../../../docs/framework/wcf/diagnostics/tracing/index.md) und [mithilfe-Ablaufverfolgung zum Beheben der Anwendung](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span><span class="sxs-lookup"><span data-stu-id="b0794-145"> tracing, see [Tracing](../../../docs/framework/wcf/diagnostics/tracing/index.md) and [Using Tracing to Troubleshoot Your Application](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0794-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0794-146">See Also</span></span>  
 [<span data-ttu-id="b0794-147">Vorgehensweise: Erstellen eines Clients</span><span class="sxs-lookup"><span data-stu-id="b0794-147">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="b0794-148">Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="b0794-148">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [<span data-ttu-id="b0794-149">Vorgehensweise: Aufrufen von Dienstvorgängen</span><span class="sxs-lookup"><span data-stu-id="b0794-149">How to: Call Service Operations Asynchronously</span></span>](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)  
 [<span data-ttu-id="b0794-150">Vorgehensweise: Zugreifen auf Dienste mit unidirektionalen und Anforderung-Antwort-Verträgen</span><span class="sxs-lookup"><span data-stu-id="b0794-150">How to: Access Services with One-Way and Request-Reply Contracts</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)  
 [<span data-ttu-id="b0794-151">Vorgehensweise: Zugriff auf einen WSE 3.0 Service</span><span class="sxs-lookup"><span data-stu-id="b0794-151">How to: Access a WSE 3.0 Service</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)  
 [<span data-ttu-id="b0794-152">Grundlagen des generierten Clientcode</span><span class="sxs-lookup"><span data-stu-id="b0794-152">Understanding Generated Client Code</span></span>](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)  
 [<span data-ttu-id="b0794-153">Vorgehensweise: Verbessern der Start Time des WCF-Clientanwendungen mit dem XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="b0794-153">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)  
 [<span data-ttu-id="b0794-154">Angeben des Clientlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="b0794-154">Specifying Client Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="b0794-155">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="b0794-155">Configuring Client Behaviors</span></span>](../../../docs/framework/wcf/configuring-client-behaviors.md)
