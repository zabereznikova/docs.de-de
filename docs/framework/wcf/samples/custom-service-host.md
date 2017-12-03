---
title: Benutzerdefinierter Diensthost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5faeb409e6076fe934d1b8c88423a8a348f786ca
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="custom-service-host"></a><span data-ttu-id="f8af0-102">Benutzerdefinierter Diensthost</span><span class="sxs-lookup"><span data-stu-id="f8af0-102">Custom Service Host</span></span>
<span data-ttu-id="f8af0-103">In diesem Beispiel wird veranschaulicht, wie mit einer benutzerdefinierten Ableitung der <xref:System.ServiceModel.ServiceHost>-Klasse das Laufzeitverhalten eines Diensts geändert wird.</span><span class="sxs-lookup"><span data-stu-id="f8af0-103">This sample demonstrates how to use a custom derivative of the <xref:System.ServiceModel.ServiceHost> class to alter the run-time behavior of a service.</span></span> <span data-ttu-id="f8af0-104">Dieser Ansatz stellt eine wiederverwendbare Alternative zum Konfigurieren einer großen Anzahl von Diensten auf die übliche Weise war.</span><span class="sxs-lookup"><span data-stu-id="f8af0-104">This approach provides a reusable alternative to configuring a large number of services in a common way.</span></span> <span data-ttu-id="f8af0-105">Außerdem zeigt das Beispiel, wie mithilfe der <xref:System.ServiceModel.Activation.ServiceHostFactory>-Klasse ein benutzerdefinierter ServiceHost in der IIS-(Internet Information Services, Internetinformationsdienste-) oder WAS-(Windows Process Activation Service-)Hostumgebung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f8af0-105">The sample also demonstrates how to use the <xref:System.ServiceModel.Activation.ServiceHostFactory> class to use a custom ServiceHost in the Internet Information Services (IIS) or Windows Process Activation Service (WAS) hosting environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8af0-106">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f8af0-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f8af0-107">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f8af0-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f8af0-108">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="f8af0-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8af0-109">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f8af0-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a><span data-ttu-id="f8af0-110">Informationen über das Szenario</span><span class="sxs-lookup"><span data-stu-id="f8af0-110">About the Scenario</span></span>  
 <span data-ttu-id="f8af0-111">Um ein unbeabsichtigtes Veröffentlichen von möglicherweise vertraulichen Dienstmetadaten zu vermeiden, wird mit der Standardkonfiguration für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienste die Metadatenveröffentlichung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f8af0-111">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services disables metadata publishing.</span></span> <span data-ttu-id="f8af0-112">Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten (wie Svcutil.exe) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f8af0-112">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
 <span data-ttu-id="f8af0-113">Wenn die Metadatenveröffentlichung für eine große Anzahl von Diensten aktiviert wird, werden jedem einzelnen Dienst die gleichen Konfigurationselemente hinzugefügt. Dies führt zu einer großen Anzahl von Konfigurationsinformationen, die weitgehend identisch sind.</span><span class="sxs-lookup"><span data-stu-id="f8af0-113">Enabling metadata publishing for a large number of services involves adding the same configuration elements to each individual service, which results in a large amount of configuration information that is essentially the same.</span></span> <span data-ttu-id="f8af0-114">Anstatt jeden Dienst einzeln zu konfigurieren, ist es möglich, imperativen Code zu schreiben, der eine einmalige Veröffentlichung der Metadaten ermöglicht. Anschließend kann dieser Code für mehrere unterschiedliche Dienste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f8af0-114">As an alternative to configuring each service individually, it is possible to write the imperative code that enables metadata publishing once and then reuse that code across several different services.</span></span> <span data-ttu-id="f8af0-115">Zu diesem Zweck wird eine neue Klasse erstellt, die von <xref:System.ServiceModel.ServiceHost> abgeleitet wird und die `ApplyConfiguration`()-Methode überschreibt, um das Metadatenveröffentlichungsverhalten imperativ hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f8af0-115">This is accomplished by creating a new class that derives from <xref:System.ServiceModel.ServiceHost> and overrides the `ApplyConfiguration`() method to imperatively add the metadata publishing behavior.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8af0-116">Beachten Sie, dass in diesem Beispiel die Erstellung eines ungesicherten Metadaten-Veröffentlichungsendpunkts veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="f8af0-116">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="f8af0-117">Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt.</span><span class="sxs-lookup"><span data-stu-id="f8af0-117">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span>  
  
## <a name="implementing-a-custom-servicehost"></a><span data-ttu-id="f8af0-118">Implementieren eines benutzerdefinierten Diensthosts</span><span class="sxs-lookup"><span data-stu-id="f8af0-118">Implementing a Custom ServiceHost</span></span>  
 <span data-ttu-id="f8af0-119">Die <xref:System.ServiceModel.ServiceHost>-Klasse macht mehrere hilfreiche virtuelle Methoden verfügbar, die von Erben überschrieben werden können, um das Laufzeitverhalten eines Diensts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f8af0-119">The <xref:System.ServiceModel.ServiceHost> class exposes several useful virtual methods that inheritors can override to alter the run-time behavior of a service.</span></span> <span data-ttu-id="f8af0-120">Beispielsweise liest die `ApplyConfiguration`()-Methode die Dienstkonfigurationsinformationen aus dem Konfigurationsspeicher und ändert die <xref:System.ServiceModel.Description.ServiceDescription> des Diensts entsprechend.</span><span class="sxs-lookup"><span data-stu-id="f8af0-120">For example, the `ApplyConfiguration`() method reads service configuration information from the configuration store and alters the host's <xref:System.ServiceModel.Description.ServiceDescription> accordingly.</span></span> <span data-ttu-id="f8af0-121">Die Standardimplementierung liest die Konfiguration aus der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f8af0-121">The default implementation reads configuration from the application’s configuration file.</span></span> <span data-ttu-id="f8af0-122">Die benutzerdefinierte Implementierung kann `ApplyConfiguration`() überschreiben, um die <xref:System.ServiceModel.Description.ServiceDescription> mithilfe von imperativem Code zu ändern oder den Standardkonfigurationsspeicher vollständig zu ersetzen,</span><span class="sxs-lookup"><span data-stu-id="f8af0-122">Custom implementations can override `ApplyConfiguration`() to further alter the <xref:System.ServiceModel.Description.ServiceDescription> using imperative code or even replace the default configuration store entirely.</span></span> <span data-ttu-id="f8af0-123">z.B. um die Endpunktkonfiguration eines Diensts aus einer Datenbank zu lesen, anstatt aus der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f8af0-123">For example, to read a service’s endpoint configuration from a database instead of the application’s configuration file.</span></span>  
  
 <span data-ttu-id="f8af0-124">In diesem Beispiel soll ein benutzerdefinierter Diensthost erstellt werden, der das ServiceMetadataBehavior hinzufügt (das die Veröffentlichung von Metadaten ermöglicht), selbst wenn dieses Verhalten in der Konfigurationsdatei des Diensts nicht ausdrücklich hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="f8af0-124">In this sample, we want to build a custom ServiceHost that adds the ServiceMetadataBehavior, (which enables metadata publishing), even if this behavior is not explicitly added in the service’s configuration file.</span></span> <span data-ttu-id="f8af0-125">Zu diesem Zweck erstellen wir eine neue Klasse, die von <xref:System.ServiceModel.ServiceHost> erbt und `ApplyConfiguration`() überschreibt.</span><span class="sxs-lookup"><span data-stu-id="f8af0-125">To accomplish this, we create a new class that inherits from <xref:System.ServiceModel.ServiceHost> and overrides `ApplyConfiguration`().</span></span>  
  
```  
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
  
 <span data-ttu-id="f8af0-126">Da die Konfigurationen in der Konfigurationsdatei der Anwendung nicht ignoriert werden sollen, wird beim Überschreiben von `ApplyConfiguration`() zuerst die Basisimplementierung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f8af0-126">Because we do not want to ignore any configuration that has been provided in the application’s configuration file, the first thing our override of `ApplyConfiguration`() does is call the base implementation.</span></span> <span data-ttu-id="f8af0-127">Nach der Fertigstellung dieser Methode kann das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> der Beschreibung imperativ mithilfe des folgenden imperativen Codes hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f8af0-127">Once this method completes, we can imperatively add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> to the description using the following imperative code.</span></span>  
  
```  
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
  
 <span data-ttu-id="f8af0-128">Die letzte Aufgabe, die beim Überschreiben von `ApplyConfiguration`() ausgeführt werden muss, ist das Hinzufügen des Standardmetadatenendpunkts.</span><span class="sxs-lookup"><span data-stu-id="f8af0-128">The last thing our `ApplyConfiguration`() override must do is add the default metadata endpoint.</span></span> <span data-ttu-id="f8af0-129">Entsprechend der Konvention wird für jeden URI in der BaseAddresses-Auflistung des Diensthosts ein Metadatenendpunkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="f8af0-129">By convention, one metadata endpoint is created for each URI in the service host’s BaseAddresses collection.</span></span>  
  
```  
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
  
## <a name="using-a-custom-servicehost-in-self-host"></a><span data-ttu-id="f8af0-130">Verwenden eines benutzerdefinierten Diensthosts bei Selbsthost</span><span class="sxs-lookup"><span data-stu-id="f8af0-130">Using a custom ServiceHost in self-host</span></span>  
 <span data-ttu-id="f8af0-131">Nachdem wir nun die Implementierung des benutzerdefinierten Diensthosts fertig gestellt haben, können wird diese verwenden, um einem beliebigen Dienst Metadatenveröffentlichungsverhalten hinzuzufügen, indem dieser Dienst innerhalb einer Instanz von `SelfDescribingServiceHost` gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f8af0-131">Now that we have completed our custom ServiceHost implementation, we can use it to add metadata publishing behavior to any service by hosting that service inside of an instance of our `SelfDescribingServiceHost`.</span></span> <span data-ttu-id="f8af0-132">Im folgenden Code wird gezeigt, wie diese im Selbsthostszenario verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f8af0-132">The following code shows how to use it in the self-host scenario.</span></span>  
  
```  
SelfDescribingServiceHost host =   
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 <span data-ttu-id="f8af0-133">Der benutzerdefinierte Host liest die Endpunktkonfiguration des Diensts nach wie vor aus der Konfigurationsdatei der Anwendung, so als wäre die <xref:System.ServiceModel.ServiceHost>-Standardklasse zum Hosten des Diensts verwendet worden.</span><span class="sxs-lookup"><span data-stu-id="f8af0-133">Our custom host still reads the service’s endpoint configuration from the application’s configuration file, just as if we had used the default <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="f8af0-134">Da jedoch in dem benutzerdefinierten Host die Logik für die Aktivierung der Metadatenveröffentlichung hinzugefügt wurde, muss das Metadatenveröffentlichungsverhalten nicht mehr explizit in der Konfiguration aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f8af0-134">However, because we added the logic to enable metadata publishing inside of our custom host, we no longer must explicitly enable the metadata publishing behavior in configuration.</span></span> <span data-ttu-id="f8af0-135">Dieser Ansatz bietet vor allem dann Vorteile, wenn Sie eine Anwendung erstellen, die mehrere Dienste enthält, und Sie die Metadatenveröffentlichung auf allen diesen Diensten aktivieren möchten, ohne jedes Mal die gleichen Konfigurationselemente schreiben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="f8af0-135">This approach has a distinct advantage when you are building an application that contains several services and you want to enable metadata publishing on each of them without writing the same configuration elements over and over.</span></span>  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a><span data-ttu-id="f8af0-136">Verwenden eines benutzerdefinierten Diensthosts in IIS oder WAS</span><span class="sxs-lookup"><span data-stu-id="f8af0-136">Using a Custom ServiceHost in IIS or WAS</span></span>  
 <span data-ttu-id="f8af0-137">Die Verwendung eines benutzerdefinierten Diensthosts in einem Selbsthostszenario ist einfach, da ausschließlich Ihr eigener Anwendungscode für die Erstellung und Öffnung der Diensthostinstanz verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="f8af0-137">Using a custom service host in self-host scenarios is straightforward, because it is your application code that is ultimately responsible for creating and opening the service host instance.</span></span> <span data-ttu-id="f8af0-138">In der IIS- oder WAS-Hostingumgebung instanziiert jedoch die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Infrastruktur dynamisch den Host Ihres Diensts als Antwort auf eingehende Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f8af0-138">In the IIS or WAS hosting environment, however, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure is dynamically instantiating your service’s host in response to incoming messages.</span></span> <span data-ttu-id="f8af0-139">Es können in dieser Hostingumgebung auch benutzerdefinierte Diensthosts verwendet werden, für diese ist jedoch zusätzlicher Code in Form einer ServiceHostFactory erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f8af0-139">Custom service hosts can also be used in this hosting environment, but they require some additional code in the form of a ServiceHostFactory.</span></span> <span data-ttu-id="f8af0-140">Im folgenden Code wird eine Ableitung von <xref:System.ServiceModel.Activation.ServiceHostFactory> dargestellt, die Instanzen des benutzerdefinierten `SelfDescribingServiceHost` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f8af0-140">The following code shows a derivative of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns instances of our custom `SelfDescribingServiceHost`.</span></span>  
  
```  
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
  
 <span data-ttu-id="f8af0-141">Wie Sie sehen können, ist die Implementierung einer benutzerdefinierten ServiceHostFactory sehr einfach.</span><span class="sxs-lookup"><span data-stu-id="f8af0-141">As you can see, implementing a custom ServiceHostFactory is very straightforward.</span></span> <span data-ttu-id="f8af0-142">Die gesamte benutzerdefinierte Logik befindet sich in der Implementierung des Diensthosts, und die Factory gibt eine Instanz der abgeleiteten Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="f8af0-142">All of the custom logic resides inside of the ServiceHost implementation; the factory returns an instance of the derived class.</span></span>  
  
 <span data-ttu-id="f8af0-143">Um eine benutzerdefinierte Factory mit einer Dienstimplementierung zu verwenden, müssen der .svc-Datei des Diensts einige zusätzlich Metadaten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f8af0-143">To use a custom factory with a service implementation, we must add some additional metadata to the service’s .svc file.</span></span>  
  
```  
<%@ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"  
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"  
               language=c# Debug="true" %>  
```  
  
 <span data-ttu-id="f8af0-144">Hier wurde der `Factory`-Direktive ein zusätzliches `@ServiceHost`-Attribut hinzugefügt, und der CLR-Typname der benutzerdefinierten Factory wurde als Attributwert übergeben.</span><span class="sxs-lookup"><span data-stu-id="f8af0-144">Here we have added an additional `Factory` attribute to the `@ServiceHost` directive, and passed the CLR type name of our custom factory as the attribute’s value.</span></span> <span data-ttu-id="f8af0-145">Wenn IIS oder WAS eine Nachricht für diesen Dienst empfängt, erstellt die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Hostinginfrastruktur zuerst eine Instanz der ServiceHostFactory und instanziiert anschließend den Diensthost durch den Aufruf von `ServiceHostFactory.CreateServiceHost()` selbst.</span><span class="sxs-lookup"><span data-stu-id="f8af0-145">When IIS or WAS receives a message for this service, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hosting infrastructure first creates an instance of the ServiceHostFactory and then instantiate the service host itself by calling `ServiceHostFactory.CreateServiceHost()`.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="f8af0-146">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="f8af0-146">Running the Sample</span></span>  
 <span data-ttu-id="f8af0-147">Auch wenn dieses Beispiel einen voll funktionsfähigen Client und Dienstimplementierung bereitstellt, ist das Ziel des Beispiels, die Änderung des Laufzeitverhaltens des Diensts mithilfe eines benutzerdefinierten Hosts zu veranschaulichen. Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f8af0-147">Although this sample does provide a fully-functional client and service implementation, the point of the sample is to illustrate how to alter a service’s run-time behavior by means of a custom host., do the following steps:</span></span>  
  
#### <a name="to-observe-the-effect-of-the-custom-host"></a><span data-ttu-id="f8af0-148">So beobachten Sie den Effekt des benutzerdefinierten Hosts</span><span class="sxs-lookup"><span data-stu-id="f8af0-148">To observe the effect of the custom host</span></span>  
  
1.  <span data-ttu-id="f8af0-149">Wenn Sie die Datei "Web.config" des Diensts öffnen, stellen Sie fest, dass keine Konfiguration explizit die Metadaten für den Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f8af0-149">Open the service’s Web.config file and observe that there is no configuration explicitly enabling metadata for the service.</span></span>  
  
2.  <span data-ttu-id="f8af0-150">Öffnen Sie die SVC Datei, und beachten Sie, dass seine @ServiceHost Richtlinie enthält eine factoryattribut, das den Namen der benutzerdefinierten ServiceHostFactory angibt.</span><span class="sxs-lookup"><span data-stu-id="f8af0-150">Open the service’s .svc file and observe that its @ServiceHost directive contains a Factory attribute that specifies the name of a custom ServiceHostFactory.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f8af0-151">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="f8af0-151">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f8af0-152">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8af0-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="f8af0-153">Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8af0-153">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="f8af0-154">Nachdem die Projektmappe erstellt wurde, führen Sie Setup.bat aus, um die ServiceModelSamples-Anwendung in [!INCLUDE[iisver](../../../../includes/iisver-md.md)] einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f8af0-154">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="f8af0-155">Das Verzeichnis ServiceModelSamples sollte jetzt als [!INCLUDE[iisver](../../../../includes/iisver-md.md)]-Anwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f8af0-155">The ServiceModelSamples directory should now appear as an [!INCLUDE[iisver](../../../../includes/iisver-md.md)] Application.</span></span>  
  
4.  <span data-ttu-id="f8af0-156">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8af0-156">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="f8af0-157">Um die Anwendung [!INCLUDE[iisver](../../../../includes/iisver-md.md)] zu entfernen, müssen Sie Cleanup.bat ausführen.</span><span class="sxs-lookup"><span data-stu-id="f8af0-157">To remove the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] application, run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8af0-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8af0-158">See Also</span></span>  
 [<span data-ttu-id="f8af0-159">How to: Host a WCF Service in IIS (Vorgehensweise: Hosten eines WCF-Diensts in IIS)</span><span class="sxs-lookup"><span data-stu-id="f8af0-159">How to: Host a WCF Service in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
