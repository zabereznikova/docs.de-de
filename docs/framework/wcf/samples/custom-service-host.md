---
title: Benutzerdefinierter Diensthost
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: 70d527599c310cba694624839f14a313f6000337
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728428"
---
# <a name="custom-service-host"></a><span data-ttu-id="c316a-102">Benutzerdefinierter Diensthost</span><span class="sxs-lookup"><span data-stu-id="c316a-102">Custom Service Host</span></span>
<span data-ttu-id="c316a-103">In diesem Beispiel wird veranschaulicht, wie mit einer benutzerdefinierten Ableitung der <xref:System.ServiceModel.ServiceHost>-Klasse das Laufzeitverhalten eines Diensts geändert wird.</span><span class="sxs-lookup"><span data-stu-id="c316a-103">This sample demonstrates how to use a custom derivative of the <xref:System.ServiceModel.ServiceHost> class to alter the run-time behavior of a service.</span></span> <span data-ttu-id="c316a-104">Dieser Ansatz stellt eine wiederverwendbare Alternative zum Konfigurieren einer großen Anzahl von Diensten auf die übliche Weise war.</span><span class="sxs-lookup"><span data-stu-id="c316a-104">This approach provides a reusable alternative to configuring a large number of services in a common way.</span></span> <span data-ttu-id="c316a-105">Außerdem zeigt das Beispiel, wie mithilfe der <xref:System.ServiceModel.Activation.ServiceHostFactory>-Klasse ein benutzerdefinierter ServiceHost in der IIS-(Internet Information Services, Internetinformationsdienste-) oder WAS-(Windows Process Activation Service-)Hostumgebung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c316a-105">The sample also demonstrates how to use the <xref:System.ServiceModel.Activation.ServiceHostFactory> class to use a custom ServiceHost in the Internet Information Services (IIS) or Windows Process Activation Service (WAS) hosting environment.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c316a-106">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c316a-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c316a-107">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c316a-107">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c316a-108">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="c316a-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c316a-109">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c316a-109">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a><span data-ttu-id="c316a-110">Informationen über das Szenario</span><span class="sxs-lookup"><span data-stu-id="c316a-110">About the scenario</span></span>
 <span data-ttu-id="c316a-111">Um eine unbeabsichtigte Offenlegung von potenziell sensiblen Dienst Metadaten zu verhindern, wird die Metadatenveröffentlichung durch die Standardkonfiguration für Windows Communication Foundation (WCF)-Dienste deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c316a-111">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="c316a-112">Dieses Verhalten ist standardmäßig sicher. Dies bedeutet aber auch, dass Sie kein metadatenimportierungstool (z. b. Svcutil. exe) verwenden können, um den Client Code zu generieren, der zum Anrufen des Dienstanbieter erforderlich ist, es sei denn, das Metadatenveröffentlichungs Verhalten des dienstan</span><span class="sxs-lookup"><span data-stu-id="c316a-112">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service's metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
 <span data-ttu-id="c316a-113">Wenn die Metadatenveröffentlichung für eine große Anzahl von Diensten aktiviert wird, werden jedem einzelnen Dienst die gleichen Konfigurationselemente hinzugefügt. Dies führt zu einer großen Anzahl von Konfigurationsinformationen, die weitgehend identisch sind.</span><span class="sxs-lookup"><span data-stu-id="c316a-113">Enabling metadata publishing for a large number of services involves adding the same configuration elements to each individual service, which results in a large amount of configuration information that is essentially the same.</span></span> <span data-ttu-id="c316a-114">Anstatt jeden Dienst einzeln zu konfigurieren, ist es möglich, imperativen Code zu schreiben, der eine einmalige Veröffentlichung der Metadaten ermöglicht. Anschließend kann dieser Code für mehrere unterschiedliche Dienste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c316a-114">As an alternative to configuring each service individually, it is possible to write the imperative code that enables metadata publishing once and then reuse that code across several different services.</span></span> <span data-ttu-id="c316a-115">Zu diesem Zweck wird eine neue Klasse erstellt, die von <xref:System.ServiceModel.ServiceHost> abgeleitet wird und die `ApplyConfiguration`()-Methode überschreibt, um das Metadatenveröffentlichungsverhalten imperativ hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c316a-115">This is accomplished by creating a new class that derives from <xref:System.ServiceModel.ServiceHost> and overrides the `ApplyConfiguration`() method to imperatively add the metadata publishing behavior.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c316a-116">Beachten Sie, dass in diesem Beispiel die Erstellung eines ungesicherten Metadaten-Veröffentlichungsendpunkts veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="c316a-116">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="c316a-117">Solche Endpunkte können für anonyme, nicht authentifizierte Consumer potenziell verfügbar sein, und vor der Bereitstellung solcher Endpunkte muss darauf geachtet werden, dass die öffentliche Offenlegung der Metadaten eines Diensts angemessen ist.</span><span class="sxs-lookup"><span data-stu-id="c316a-117">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service's metadata is appropriate.</span></span>  
  
## <a name="implementing-a-custom-servicehost"></a><span data-ttu-id="c316a-118">Implementieren eines benutzerdefinierten Diensthosts</span><span class="sxs-lookup"><span data-stu-id="c316a-118">Implementing a custom ServiceHost</span></span>
 <span data-ttu-id="c316a-119">Die <xref:System.ServiceModel.ServiceHost>-Klasse macht mehrere hilfreiche virtuelle Methoden verfügbar, die von Erben überschrieben werden können, um das Laufzeitverhalten eines Diensts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c316a-119">The <xref:System.ServiceModel.ServiceHost> class exposes several useful virtual methods that inheritors can override to alter the run-time behavior of a service.</span></span> <span data-ttu-id="c316a-120">Beispielsweise liest die `ApplyConfiguration`()-Methode die Dienstkonfigurationsinformationen aus dem Konfigurationsspeicher und ändert die <xref:System.ServiceModel.Description.ServiceDescription> des Diensts entsprechend.</span><span class="sxs-lookup"><span data-stu-id="c316a-120">For example, the `ApplyConfiguration`() method reads service configuration information from the configuration store and alters the host's <xref:System.ServiceModel.Description.ServiceDescription> accordingly.</span></span> <span data-ttu-id="c316a-121">Die Standard Implementierung liest die Konfiguration aus der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c316a-121">The default implementation reads configuration from the application's configuration file.</span></span> <span data-ttu-id="c316a-122">Die benutzerdefinierte Implementierung kann `ApplyConfiguration`() überschreiben, um die <xref:System.ServiceModel.Description.ServiceDescription> mithilfe von imperativem Code zu ändern oder den Standardkonfigurationsspeicher vollständig zu ersetzen,</span><span class="sxs-lookup"><span data-stu-id="c316a-122">Custom implementations can override `ApplyConfiguration`() to further alter the <xref:System.ServiceModel.Description.ServiceDescription> using imperative code or even replace the default configuration store entirely.</span></span> <span data-ttu-id="c316a-123">So können Sie z. b. die Endpunkt Konfiguration eines dienstanaus einer Datenbank anstelle der Konfigurationsdatei der Anwendung lesen.</span><span class="sxs-lookup"><span data-stu-id="c316a-123">For example, to read a service's endpoint configuration from a database instead of the application's configuration file.</span></span>  
  
 <span data-ttu-id="c316a-124">In diesem Beispiel möchten wir einen benutzerdefinierten Service Host erstellen, der das ServiceMetadataBehavior (das die Metadatenveröffentlichung ermöglicht) hinzufügt, auch wenn dieses Verhalten nicht explizit in der Konfigurationsdatei des Diensts hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c316a-124">In this sample, we want to build a custom ServiceHost that adds the ServiceMetadataBehavior (which enables metadata publishing) even if this behavior is not explicitly added in the service's configuration file.</span></span> <span data-ttu-id="c316a-125">Um dies zu erreichen, erstellen Sie eine neue Klasse, die <xref:System.ServiceModel.ServiceHost> von erbt `ApplyConfiguration`und () überschreibt.</span><span class="sxs-lookup"><span data-stu-id="c316a-125">To accomplish this, create a new class that inherits from <xref:System.ServiceModel.ServiceHost> and overrides `ApplyConfiguration`().</span></span>  
  
```csharp
class SelfDescribingServiceHost : ServiceHost  
{  
    public SelfDescribingServiceHost(Type serviceType, params Uri[] baseAddresses)  
        : base(serviceType, baseAddresses) { }  
  
    //Overriding ApplyConfiguration() allows us to
    //alter the ServiceDescription prior to opening  
    //the service host.
    protected override void ApplyConfiguration()  
    {  
        //First, we call base.ApplyConfiguration()  
        //to read any configuration that was provided for  
        //the service we're hosting. After this call,  
        //this.Description describes the service  
        //as it was configured.  
        base.ApplyConfiguration();
  
        //(rest of implementation elided for clarity)  
    }  
}  
```  
  
 <span data-ttu-id="c316a-126">Da keine Konfiguration ignoriert werden soll, die in der Konfigurationsdatei der Anwendung bereitgestellt wurde, wird als erstes bei der außer Kraft Setzung `ApplyConfiguration`von () die Basis Implementierung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c316a-126">Because we do not want to ignore any configuration that has been provided in the application's configuration file, the first thing our override of `ApplyConfiguration`() does is call the base implementation.</span></span> <span data-ttu-id="c316a-127">Nach der Fertigstellung dieser Methode kann das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> der Beschreibung imperativ mithilfe des folgenden imperativen Codes hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c316a-127">Once this method completes, we can imperatively add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> to the description using the following imperative code.</span></span>  
  
```csharp
ServiceMetadataBehavior mexBehavior = this.Description.Behaviors.Find<ServiceMetadataBehavior>();  
if (mexBehavior == null)  
{  
    mexBehavior = new ServiceMetadataBehavior();  
    this.Description.Behaviors.Add(mexBehavior);  
}  
else  
{  
    //Metadata behavior has already been configured,
    //so we do not have any work to do.  
    return;  
}  
```  
  
 <span data-ttu-id="c316a-128">Die letzte Aufgabe, die beim Überschreiben von `ApplyConfiguration`() ausgeführt werden muss, ist das Hinzufügen des Standardmetadatenendpunkts.</span><span class="sxs-lookup"><span data-stu-id="c316a-128">The last thing our `ApplyConfiguration`() override must do is add the default metadata endpoint.</span></span> <span data-ttu-id="c316a-129">Gemäß der Konvention wird für jeden URI in der baseadressen-Auflistung des Dienst Hosts ein Metadatenendpunkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="c316a-129">By convention, one metadata endpoint is created for each URI in the service host's BaseAddresses collection.</span></span>  
  
```csharp
//Add a metadata endpoint at each base address  
//using the "/mex" addressing convention  
foreach (Uri baseAddress in this.BaseAddresses)  
{  
    if (baseAddress.Scheme == Uri.UriSchemeHttp)  
    {  
        mexBehavior.HttpGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeHttps)  
    {  
        mexBehavior.HttpsGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpsBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetPipe)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexNamedPipeBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetTcp)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexTcpBinding(),  
                                "mex");  
    }  
}  
```  
  
## <a name="using-a-custom-servicehost-in-self-host"></a><span data-ttu-id="c316a-130">Verwenden eines benutzerdefinierten Diensthosts bei Selbsthost</span><span class="sxs-lookup"><span data-stu-id="c316a-130">Using a custom ServiceHost in self-host</span></span>  
 <span data-ttu-id="c316a-131">Nachdem wir nun die Implementierung des benutzerdefinierten Diensthosts fertig gestellt haben, können wird diese verwenden, um einem beliebigen Dienst Metadatenveröffentlichungsverhalten hinzuzufügen, indem dieser Dienst innerhalb einer Instanz von `SelfDescribingServiceHost` gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="c316a-131">Now that we have completed our custom ServiceHost implementation, we can use it to add metadata publishing behavior to any service by hosting that service inside of an instance of our `SelfDescribingServiceHost`.</span></span> <span data-ttu-id="c316a-132">Im folgenden Code wird gezeigt, wie diese im Selbsthostszenario verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c316a-132">The following code shows how to use it in the self-host scenario.</span></span>  
  
```csharp
SelfDescribingServiceHost host =
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 <span data-ttu-id="c316a-133">Der benutzerdefinierte Host liest weiterhin die Endpunkt Konfiguration des Diensts aus der Konfigurationsdatei der Anwendung, so als ob wir die <xref:System.ServiceModel.ServiceHost> Standardklasse zum Hosten des Diensts verwendet hätten.</span><span class="sxs-lookup"><span data-stu-id="c316a-133">Our custom host still reads the service's endpoint configuration from the application's configuration file, as if we had used the default <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="c316a-134">Da jedoch in dem benutzerdefinierten Host die Logik für die Aktivierung der Metadatenveröffentlichung hinzugefügt wurde, muss das Metadatenveröffentlichungsverhalten nicht mehr explizit in der Konfiguration aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c316a-134">However, because we added the logic to enable metadata publishing inside of our custom host, we no longer must explicitly enable the metadata publishing behavior in configuration.</span></span> <span data-ttu-id="c316a-135">Dieser Ansatz bietet vor allem dann Vorteile, wenn Sie eine Anwendung erstellen, die mehrere Dienste enthält, und Sie die Metadatenveröffentlichung auf allen diesen Diensten aktivieren möchten, ohne jedes Mal die gleichen Konfigurationselemente schreiben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c316a-135">This approach has a distinct advantage when you are building an application that contains several services and you want to enable metadata publishing on each of them without writing the same configuration elements over and over.</span></span>  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a><span data-ttu-id="c316a-136">Verwenden eines benutzerdefinierten Diensthosts in IIS oder WAS</span><span class="sxs-lookup"><span data-stu-id="c316a-136">Using a custom ServiceHost in IIS or WAS</span></span>  
 <span data-ttu-id="c316a-137">Die Verwendung eines benutzerdefinierten Diensthosts in einem Selbsthostszenario ist einfach, da ausschließlich Ihr eigener Anwendungscode für die Erstellung und Öffnung der Diensthostinstanz verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="c316a-137">Using a custom service host in self-host scenarios is straightforward, because it is your application code that is ultimately responsible for creating and opening the service host instance.</span></span> <span data-ttu-id="c316a-138">In der IIS-oder was-Hostingumgebung instanziiert die WCF-Infrastruktur jedoch den Host Ihres Diensts dynamisch als Reaktion auf eingehende Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c316a-138">In the IIS or WAS hosting environment, however, the WCF infrastructure is dynamically instantiating your service's host in response to incoming messages.</span></span> <span data-ttu-id="c316a-139">Es können in dieser Hostingumgebung auch benutzerdefinierte Diensthosts verwendet werden, für diese ist jedoch zusätzlicher Code in Form einer ServiceHostFactory erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c316a-139">Custom service hosts can also be used in this hosting environment, but they require some additional code in the form of a ServiceHostFactory.</span></span> <span data-ttu-id="c316a-140">Im folgenden Code wird eine Ableitung von <xref:System.ServiceModel.Activation.ServiceHostFactory> dargestellt, die Instanzen des benutzerdefinierten `SelfDescribingServiceHost` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c316a-140">The following code shows a derivative of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns instances of our custom `SelfDescribingServiceHost`.</span></span>  
  
```csharp
public class SelfDescribingServiceHostFactory : ServiceHostFactory  
{  
    protected override ServiceHost CreateServiceHost(Type serviceType,
     Uri[] baseAddresses)  
    {  
        //All the custom factory does is return a new instance  
        //of our custom host class. The bulk of the custom logic should  
        //live in the custom host (as opposed to the factory)
        //for maximum  
        //reuse value outside of the IIS/WAS hosting environment.  
        return new SelfDescribingServiceHost(serviceType,
                                             baseAddresses);  
    }  
}  
```  
  
 <span data-ttu-id="c316a-141">Wie Sie sehen können, ist die Implementierung einer benutzerdefinierten ServiceHostFactory unkompliziert.</span><span class="sxs-lookup"><span data-stu-id="c316a-141">As you can see, implementing a custom ServiceHostFactory is straightforward.</span></span> <span data-ttu-id="c316a-142">Die gesamte benutzerdefinierte Logik befindet sich in der Implementierung des Diensthosts, und die Factory gibt eine Instanz der abgeleiteten Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="c316a-142">All of the custom logic resides inside of the ServiceHost implementation; the factory returns an instance of the derived class.</span></span>  
  
 <span data-ttu-id="c316a-143">Damit eine benutzerdefinierte Factory mit einer Dienst Implementierung verwendet werden kann, müssen der SVC-Datei des dienstanteils zusätzliche Metadaten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c316a-143">To use a custom factory with a service implementation, we must add some additional metadata to the service's .svc file.</span></span>  
  
```xml
<% @ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"
               language=c# Debug="true" %>
```
  
 <span data-ttu-id="c316a-144">Hier haben wir ein zusätzliches `Factory` Attribut zur- `@ServiceHost` Direktive hinzugefügt und den CLR-Typnamen der benutzerdefinierten Factory als Attribut Wert weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="c316a-144">Here we have added an additional `Factory` attribute to the `@ServiceHost` directive, and passed the CLR type name of our custom factory as the attribute's value.</span></span> <span data-ttu-id="c316a-145">Wenn IIS oder was eine Nachricht für diesen Dienst empfängt, erstellt die WCF-Hostinginfrastruktur zunächst eine Instanz von ServiceHostFactory und instanziiert dann den Dienst Host `ServiceHostFactory.CreateServiceHost()`selbst durch Aufrufen von.</span><span class="sxs-lookup"><span data-stu-id="c316a-145">When IIS or WAS receives a message for this service, the WCF hosting infrastructure first creates an instance of the ServiceHostFactory and then instantiates the service host itself by calling `ServiceHostFactory.CreateServiceHost()`.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="c316a-146">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="c316a-146">Running the sample</span></span>  
 <span data-ttu-id="c316a-147">Obwohl dieses Beispiel eine voll funktionsfähige Client-und Dienst Implementierung bereitstellt, besteht der Punkt des Beispiels darin, zu veranschaulichen, wie das Laufzeitverhalten eines Diensts mithilfe eines benutzerdefinierten Hosts geändert werden kann. führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c316a-147">Although this sample does provide a fully functional client and service implementation, the point of the sample is to illustrate how to alter a service's run-time behavior by means of a custom host., do the following steps:</span></span>  
  
### <a name="observe-the-effect-of-the-custom-host"></a><span data-ttu-id="c316a-148">Beobachten der Auswirkung des benutzerdefinierten Hosts</span><span class="sxs-lookup"><span data-stu-id="c316a-148">Observe the effect of the custom host</span></span>
  
1. <span data-ttu-id="c316a-149">Öffnen Sie die Datei "Web. config" des Diensts, und beachten Sie, dass keine Konfiguration explizit die Metadaten für den Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c316a-149">Open the service's Web.config file and observe that there is no configuration explicitly enabling metadata for the service.</span></span>  
  
2. <span data-ttu-id="c316a-150">Öffnen Sie die SVC-Datei des dienstanders, @ServiceHost und beobachten Sie, dass die-Direktive ein Factory-Attribut enthält, das den Namen einer benutzerdefinierten ServiceHostFactory angibt.</span><span class="sxs-lookup"><span data-stu-id="c316a-150">Open the service's .svc file and observe that its @ServiceHost directive contains a Factory attribute that specifies the name of a custom ServiceHostFactory.</span></span>  
  
### <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="c316a-151">Einrichten, erstellen und Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="c316a-151">Set up, build, and run the sample</span></span>
  
1. <span data-ttu-id="c316a-152">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="c316a-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="c316a-153">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c316a-153">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="c316a-154">Nachdem die Projekt Mappe erstellt wurde, führen Sie Setup. bat aus, um die Service Model Samples-Anwendung in IIS 7,0 einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c316a-154">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="c316a-155">Das Verzeichnis Service Model Samples sollte jetzt als IIS 7,0-Anwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c316a-155">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="c316a-156">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c316a-156">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

5. <span data-ttu-id="c316a-157">Um die IIS 7,0-Anwendung zu entfernen, führen Sie *Cleanup. bat*aus.</span><span class="sxs-lookup"><span data-stu-id="c316a-157">To remove the IIS 7.0 application, run *Cleanup.bat*.</span></span>

## <a name="see-also"></a><span data-ttu-id="c316a-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c316a-158">See also</span></span>

- [<span data-ttu-id="c316a-159">Vorgehensweise: Hosten eines WCF-Diensts in IIS</span><span class="sxs-lookup"><span data-stu-id="c316a-159">How to: Host a WCF Service in IIS</span></span>](../feature-details/how-to-host-a-wcf-service-in-iis.md)
