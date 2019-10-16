---
title: Zugreifen auf Dienste mithilfe eines WCF-Clients
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: 462d9a3923009f0124c2b90b6fa86dfa9869a3c5
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72316536"
---
# <a name="accessing-services-using-a-wcf-client"></a><span data-ttu-id="1ec6e-102">Zugreifen auf Dienste mithilfe eines WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="1ec6e-102">Accessing Services Using a WCF Client</span></span>

<span data-ttu-id="1ec6e-103">Nachdem Sie einen Dienst erstellt haben, ist der nächste Schritt das Erstellen eines WCF-Client Proxys.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-103">After you create a service, the next step is to create a WCF client proxy.</span></span> <span data-ttu-id="1ec6e-104">Eine Client Anwendung verwendet den WCF-Client Proxy, um mit dem Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-104">A client application uses the WCF client proxy to communicate with the service.</span></span> <span data-ttu-id="1ec6e-105">Client Anwendungen importieren in der Regel die Metadaten eines dienstanders, um WCF-Client Code zu generieren, mit dem der Dienst aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-105">Client applications usually import a service's metadata to generate WCF client code that can be used to invoke the service.</span></span>

 <span data-ttu-id="1ec6e-106">Die grundlegenden Schritte zum Erstellen eines WCF-Clients umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1ec6e-106">The basic steps for creating a WCF client include the following:</span></span>

1. <span data-ttu-id="1ec6e-107">Kompilieren Sie den Dienstcode.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-107">Compile the service code.</span></span>

2. <span data-ttu-id="1ec6e-108">Generieren Sie den WCF-Client Proxy.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-108">Generate the WCF client proxy.</span></span>

3. <span data-ttu-id="1ec6e-109">Instanziieren Sie den WCF-Clientproxy.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-109">Instantiate the WCF client proxy.</span></span>

<span data-ttu-id="1ec6e-110">Der WCF-Client Proxy kann mithilfe des Service Model Metadata Utility Tool (Svcutil. exe) manuell generiert werden. Weitere Informationen finden Sie unter [Service Model Metadata Utility-Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1ec6e-110">The WCF client proxy can be generated manually by using the Service Model Metadata Utility Tool (SvcUtil.exe) for more information see, [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="1ec6e-111">Der WCF-Client Proxy kann auch in Visual Studio mithilfe der **Dienstverweis hinzufügen** -Funktion generiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-111">The WCF client proxy can also be generated within Visual Studio using the **Add Service Reference**  feature.</span></span> <span data-ttu-id="1ec6e-112">Um den WCF-Clientproxy mithilfe einer dieser Methoden zu generieren, muss der Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-112">To generate the WCF client proxy using either method the service must be running.</span></span> <span data-ttu-id="1ec6e-113">Wenn es sich um einen selbst gehosteten Dienst handelt, müssen Sie den Host ausführen.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-113">If the service is self-hosted you must run the host.</span></span> <span data-ttu-id="1ec6e-114">Wenn der Dienst in IIS/WAS gehostet wird, ist kein weiterer Schritt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-114">If the service is hosted in IIS/WAS you do not need to do anything else.</span></span>

## <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="1ec6e-115">ServiceModel Metadata Utility Tool</span><span class="sxs-lookup"><span data-stu-id="1ec6e-115">ServiceModel Metadata Utility Tool</span></span>
 <span data-ttu-id="1ec6e-116">Das [Service Model Metadata Utility-Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) ist ein Befehlszeilen Tool zum Erstellen von Code aus Metadaten.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-116">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) is a command-line tool for generating code from metadata.</span></span> <span data-ttu-id="1ec6e-117">Die folgende Verwendung ist ein Beispiel für einen grundlegenden Svcutil.exe-Befehl.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-117">The following use is an example of a basic Svcutil.exe command.</span></span>

```console
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
```

 <span data-ttu-id="1ec6e-118">Alternativ können Sie Svcutil.exe mit WSDL (Web Services Description Language) und XSD (XML Schema Definition Language)-Dateien im Dateisystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-118">Alternatively, you can use Svcutil.exe with Web Services Description Language (WSDL) and XML Schema definition language (XSD) files on the file system.</span></span>

```console
Svcutil.exe <list of WSDL and XSD files on file system>
```

 <span data-ttu-id="1ec6e-119">Das Ergebnis ist eine Codedatei, die WCF-Client Code enthält, den die Client Anwendung verwenden kann, um den Dienst aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-119">The result is a code file that contains WCF client code that the client application can use to invoke the service.</span></span>

 <span data-ttu-id="1ec6e-120">Sie können das Tool auch zum Generieren von Konfigurationsdateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-120">You can also use the tool to generate configuration files.</span></span>

```console
Svcutil.exe <file1 [,file2]>
```

 <span data-ttu-id="1ec6e-121">Wenn nur ein Dateiname angegeben wird, ist das der Name der Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-121">If only one file name is given, that is the name of the output file.</span></span> <span data-ttu-id="1ec6e-122">Wenn zwei Dateinamen angegeben werden, ist die erste Datei eine Eingabekonfigurationsdatei, deren Inhalt mit der generierten Konfiguration zusammengeführt und in die zweite Datei geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-122">If two file names are given, then the first file is an input configuration file whose contents are merged with the generated configuration and written out into the second file.</span></span> <span data-ttu-id="1ec6e-123">Weitere Informationen zur Konfiguration finden Sie unter [Konfigurieren von Bindungen für Dienste](configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="1ec6e-123">For more information about configuration, see [Configuring Bindings for Services](configuring-bindings-for-wcf-services.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ec6e-124">Nicht gesicherte Metadatenanforderungen stellen genau wie nicht gesicherte Netzwerkanforderungen ein gewisses Risiko dar: Wenn Sie sich nicht sicher sind, ob der Endpunkt, mit dem Sie kommunizieren, der vorgegebenen Identität entspricht, stammen die abgerufenen Informationen unter Umständen von einem bösartigen Dienst.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-124">Unsecured metadata requests pose certain risks in the same way that any unsecured network request does: If you are not certain that the endpoint you are communicating with is who it says it is, the information you retrieve might be metadata from a malicious service.</span></span>

## <a name="add-service-reference-in-visual-studio"></a><span data-ttu-id="1ec6e-125">"Dienstverweis hinzufügen" in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1ec6e-125">Add Service Reference in Visual Studio</span></span>

 <span data-ttu-id="1ec6e-126">Wenn der Dienst ausgeführt wird, **Klicken Sie mit**der rechten Maustaste auf das Projekt, das den WCF-Client Proxy enthalten soll, und wählen Sie  > -**Dienst Verweis**</span><span class="sxs-lookup"><span data-stu-id="1ec6e-126">With the service running, right click the project that will contain the WCF client proxy and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="1ec6e-127">Geben Sie im **Dialog Feld Dienstverweis hinzufügen**die URL zu dem Dienst ein, den Sie aufrufen möchten, und klicken Sie auf die Schaltfläche **Gehe** zu.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-127">In the **Add Service Reference Dialog**, type in the URL to the service you want to call and click the **Go** button.</span></span> <span data-ttu-id="1ec6e-128">Das Dialogfeld zeigt eine Liste der Dienste an, die unter der Adresse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-128">The dialog will display a list of services available at the address you specify.</span></span> <span data-ttu-id="1ec6e-129">Doppelklicken Sie auf den Dienst, um die verfügbaren Verträge und Vorgänge anzuzeigen, geben Sie einen Namespace für den generierten Code an, und klicken Sie auf die Schaltfläche **OK** .</span><span class="sxs-lookup"><span data-stu-id="1ec6e-129">Double click the service to see the contracts and operations available, specify a namespace for the generated code, and click the **OK** button.</span></span>

## <a name="example"></a><span data-ttu-id="1ec6e-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ec6e-130">Example</span></span>
 <span data-ttu-id="1ec6e-131">Im folgenden Codebeispiel wird ein für einen Dienst erstellter Dienstvertrag gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-131">The following code example shows a service contract created for a service.</span></span>

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

 <span data-ttu-id="1ec6e-132">Das Service Model Metadata Utility-Tool und **Dienstverweis hinzufügen** in Visual Studio generieren die folgende WCF-Client Klasse.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-132">The ServiceModel Metadata utility tool and **Add Service Reference** in Visual Studio generates the following WCF client class.</span></span> <span data-ttu-id="1ec6e-133">Die Klasse erbt von der generischen <xref:System.ServiceModel.ClientBase%601>-Klasse und implementiert die `ICalculator`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-133">The class inherits from the generic <xref:System.ServiceModel.ClientBase%601> class and implements the `ICalculator` interface.</span></span> <span data-ttu-id="1ec6e-134">Das Tool generiert auch die `ICalculator`-Schnittstelle (wird hier nicht gezeigt).</span><span class="sxs-lookup"><span data-stu-id="1ec6e-134">The tool also generates the `ICalculator` interface (not shown here).</span></span>

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

## <a name="using-the-wcf-client"></a><span data-ttu-id="1ec6e-135">Verwenden des WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="1ec6e-135">Using the WCF Client</span></span>
 <span data-ttu-id="1ec6e-136">Um den WCF-Client zu verwenden, erstellen Sie eine Instanz des WCF-Clients, und rufen Sie dann die zugehörigen Methoden auf, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-136">To use the WCF client, create an instance of the WCF client, and then call its methods, as shown in the following code.</span></span>

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

## <a name="debugging-exceptions-thrown-by-a-client"></a><span data-ttu-id="1ec6e-137">Debuggen der von einem Client ausgelösten Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="1ec6e-137">Debugging Exceptions Thrown by a Client</span></span>

<span data-ttu-id="1ec6e-138">Viele von einem WCF-Client ausgelöste Ausnahmen werden durch eine Ausnahme auf dem Dienst verursacht.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-138">Many exceptions thrown by a WCF client are caused by an exception on the service.</span></span> <span data-ttu-id="1ec6e-139">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="1ec6e-139">Some examples of this are:</span></span>

- <span data-ttu-id="1ec6e-140"><xref:System.Net.Sockets.SocketException>: Vom Remotehost wurde die Schließung einer bestehenden Verbindung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-140"><xref:System.Net.Sockets.SocketException>: An existing connection was forcibly closed by the remote host.</span></span>

- <span data-ttu-id="1ec6e-141"><xref:System.ServiceModel.CommunicationException>: Die zugrunde liegende Verbindung wurde unerwartet geschlossen.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-141"><xref:System.ServiceModel.CommunicationException>: The underlying connection was closed unexpectedly.</span></span>

- <span data-ttu-id="1ec6e-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: Die Socketverbindung wurde abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: The socket connection was aborted.</span></span> <span data-ttu-id="1ec6e-143">Mögliche Ursache: Ein Fehler beim Verarbeiten der Nachricht, eine Zeitüberschreitung durch den Remotehost beim Empfang oder ein Problem mit einer zugrunde liegenden Netzwerkressource.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-143">This could be caused by an error processing your message, a receive time-out being exceeded by the remote host, or an underlying network resource issue.</span></span>

<span data-ttu-id="1ec6e-144">Tritt eine Ausnahme dieses Typs auf, aktivieren Sie die Ablaufverfolgung auf der Dienstseite, und ermitteln Sie die dort aufgetretene Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-144">When these types of exceptions occur, the best way to solve the problem is to turn on tracing on the service side and determine what exception occurred there.</span></span> <span data-ttu-id="1ec6e-145">Weitere Informationen zur [Ablauf Verfolgung finden](./diagnostics/tracing/index.md) Sie unter Ablauf Verfolgung und [Verwenden der Ablauf Verfolgung für](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)die Problembehandlung Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1ec6e-145">For more information about tracing, see [Tracing](./diagnostics/tracing/index.md) and [Using Tracing to Troubleshoot Your Application](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ec6e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ec6e-146">See also</span></span>

- [<span data-ttu-id="1ec6e-147">Vorgehensweise: Erstellen eines Clients</span><span class="sxs-lookup"><span data-stu-id="1ec6e-147">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [<span data-ttu-id="1ec6e-148">Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="1ec6e-148">How to: Access Services with a Duplex Contract</span></span>](./feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="1ec6e-149">Vorgehensweise: Asynchrones Aufrufen von Dienstvorgängen</span><span class="sxs-lookup"><span data-stu-id="1ec6e-149">How to: Call Service Operations Asynchronously</span></span>](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [<span data-ttu-id="1ec6e-150">Vorgehensweise: Zugreifen auf Dienste mit unidirektionalen und Anforderung-Antwort-Verträgen</span><span class="sxs-lookup"><span data-stu-id="1ec6e-150">How to: Access Services with One-Way and Request-Reply Contracts</span></span>](./feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [<span data-ttu-id="1ec6e-151">Vorgehensweise: Zugriff auf einen WSE3.0-Dienst</span><span class="sxs-lookup"><span data-stu-id="1ec6e-151">How to: Access a WSE 3.0 Service</span></span>](./feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [<span data-ttu-id="1ec6e-152">Grundlagen des generierten Clientcodes</span><span class="sxs-lookup"><span data-stu-id="1ec6e-152">Understanding Generated Client Code</span></span>](./feature-details/understanding-generated-client-code.md)
- [<span data-ttu-id="1ec6e-153">Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="1ec6e-153">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
- [<span data-ttu-id="1ec6e-154">Angeben des Clientlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="1ec6e-154">Specifying Client Run-Time Behavior</span></span>](specifying-client-run-time-behavior.md)
- [<span data-ttu-id="1ec6e-155">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="1ec6e-155">Configuring Client Behaviors</span></span>](configuring-client-behaviors.md)
