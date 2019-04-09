---
title: 'Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration'
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: caaa89573d272c5d11d179b08c2d9e24c76d21e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140620"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a><span data-ttu-id="0c7c5-102">Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0c7c5-102">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>
<span data-ttu-id="0c7c5-103">Windows Communication Foundation (WCF) ermöglicht Ihnen die Erstellung ein Diensts, das einen ASP.NET AJAX-aktivierten Endpunkt verfügbar macht, der auf einer Client-Website von JavaScript aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="0c7c5-104">Zum Erstellen eines solchen Endpunkts können Sie entweder (wie bei allen anderen WCF-Endpunkten) eine Konfigurationsdatei verwenden, oder Sie können eine Methode einsetzen, die keine Konfigurationselemente benötigt.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-104">To create such an endpoint, you can either use a configuration file, as with all other WCF endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="0c7c5-105">In diesem Thema wird die zweite Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-105">This topic demonstrates the second approach.</span></span>  
  
 <span data-ttu-id="0c7c5-106">Um Dienste mit ASP.NET AJAX-Endpunkten ohne Konfiguration zu erstellen, müssen diese Dienste von Internetinformationsdiensten (IIS) gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-106">To create services with ASP.NET AJAX endpoints without configuration, the services must be hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="0c7c5-107">Um einen ASP.NET AJAX-Endpunkt, der mit diesem Ansatz zu aktivieren, geben Sie die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> als Parameter für die Factory in der [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive in der SVC-Datei.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-107">To activate an ASP.NET AJAX endpoint using this approach, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> as the Factory parameter in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive in the .svc file.</span></span> <span data-ttu-id="0c7c5-108">Diese benutzerdefinierte Factory ist die Komponente, die automatisch einen ASP.NET AJAX-Endpunkt konfiguriert, damit er auf einer Client-Website von JavaScript aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-108">This custom factory is the component that automatically configures an ASP.NET AJAX endpoint so that it can be called from JavaScript on a client Web site.</span></span>  
  
 <span data-ttu-id="0c7c5-109">Ein Arbeitsbeispiel finden Sie unter den [AJAX-Dienst ohne Konfiguration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="0c7c5-109">For a working example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
 <span data-ttu-id="0c7c5-110">Eine Übersicht über ASP.NET AJAX-Endpunkt mithilfe von Konfigurationselementen konfigurieren, finden Sie unter [Vorgehensweise: Verwenden Sie die Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="0c7c5-110">For an outline of how to configure an ASP.NET AJAX endpoint using configuration elements, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="0c7c5-111">So erstellen Sie einen WCF-Basisdienst</span><span class="sxs-lookup"><span data-stu-id="0c7c5-111">To create a basic WCF service</span></span>  
  
1.  <span data-ttu-id="0c7c5-112">Definieren ein grundlegenden WCF-Dienstvertrags mit einer Schnittstelle markiert mit dem <xref:System.ServiceModel.ServiceContractAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-112">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="0c7c5-113">Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-113">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="0c7c5-114">Stellen Sie sicher, dass Sie die <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-114">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```csharp  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  <span data-ttu-id="0c7c5-115">Implementieren Sie den `ICalculator`-Dienstvertrag mit `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-115">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  <span data-ttu-id="0c7c5-116">Definieren Sie einen Namespace für die `ICalculator`- und die `CalculatorService`-Implementierung, indem Sie sie in einen Namespaceblock einschließen.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-116">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a><span data-ttu-id="0c7c5-117">So hosten Sie einen Dienst in Internetinformationsdiensten (IIS) ohne Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0c7c5-117">To host the service in Internet Information Services without configuration</span></span>  
  
1.  <span data-ttu-id="0c7c5-118">Erstellen Sie eine neue Datei mit einer SVC-Erweiterung in der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-118">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="0c7c5-119">Bearbeiten Sie diese Datei durch Hinzufügen des entsprechenden [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -direktiveninformationen für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-119">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="0c7c5-120">Angeben, die die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> in verwendet werden soll die [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie, um einen ASP.NET AJAX-Endpunkt automatisch zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-120">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2.  <span data-ttu-id="0c7c5-121">Erstellen Sie den Dienst, und rufen Sie ihn vom Client aus auf.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-121">Build the service and call it from the client.</span></span> <span data-ttu-id="0c7c5-122">Internetinformationsdienste (IIS) aktiviert den Dienst, sobald er aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-122">Internet Information Services (IIS) activates the service when called.</span></span> <span data-ttu-id="0c7c5-123">Weitere Informationen zum Hosten in IIS finden Sie unter [Vorgehensweise: Hosten ein WCF-Diensts in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="0c7c5-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="0c7c5-124">So rufen Sie den Dienst auf</span><span class="sxs-lookup"><span data-stu-id="0c7c5-124">To call the service</span></span>  
  
1.  <span data-ttu-id="0c7c5-125">Der Endpunkt wird an einer leeren Adresse relativ zur SVC-Datei konfiguriert, damit der Dienst jetzt verfügbar ist und aufgerufen werden, kann durch das Senden von Anforderungen an service.svc/\<Vorgang > – z. B. service.svc/Add für die `Add` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="0c7c5-126">Sie können ihn verwenden, indem Sie die Dienst-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-126">You can use it by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="0c7c5-127">Ein Beispiel finden Sie unter den [AJAX-Dienst ohne Konfiguration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="0c7c5-127">For an example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c7c5-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c7c5-128">Example</span></span>  
  
 <span data-ttu-id="0c7c5-129">Der automatisch konfigurierte Endpunkt wird bei einer leeren Adresse relativ zur Basis-URL erstellt.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-129">The automatically-configured endpoint is created at an empty address relative to the base URL.</span></span> <span data-ttu-id="0c7c5-130">Bei diesem Ansatz wird auch eine Konfigurationsdatei hinzugefügt und verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-130">A configuration file can also be added and used with this approach.</span></span> <span data-ttu-id="0c7c5-131">Wenn die Konfigurationsdatei Endpunktdefinitionen enthält, werden diese Endpunkte dem automatisch konfigurierten Endpunkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-131">If the configuration file contains endpoint definitions, these endpoints are added to the automatically-configured endpoint.</span></span>  
  
 <span data-ttu-id="0c7c5-132">Die Datei "service.svc" verwendet beispielsweise die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, und das Dienstverzeichnis enthält eine Web.config-Datei, die mithilfe der <xref:System.ServiceModel.BasicHttpBinding> einen Endpunkt für den gleichen Dienst definiert, wobei für diesen eine zu "soap" relative Adresse angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-132">For example, service.svc uses the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> and the service directory contains a Web.config file that defines an endpoint for the same service using the <xref:System.ServiceModel.BasicHttpBinding> at the "soap" relative address.</span></span> <span data-ttu-id="0c7c5-133">In diesem Fall enthält der Dienst zwei Endpunkte: einen unter service.svc (der auf ASP.NET AJAX-Anforderungen antwortet) und einen weiteren unter service.svc/soap (der auf SOAP-Anforderungen antwortet).</span><span class="sxs-lookup"><span data-stu-id="0c7c5-133">In this case, the service contains two endpoints: one at service.svc (which responds to ASP.NET AJAX requests) and another at service.svc/soap (which responds to SOAP requests).</span></span>  
  
 <span data-ttu-id="0c7c5-134">Definiert die Konfigurationsdatei einen Endpunkt unter einer leeren relativen Adresse und wird <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> verwendet, wird eine Ausnahme ausgelöst, und der Start des Diensts schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-134">If the configuration file defines an endpoint at an empty relative address and the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used, an exception is thrown and the service fails to start.</span></span>  
  
 <span data-ttu-id="0c7c5-135">Sie können die Konfiguration nicht dazu verwenden, Einstellungen auf dem automatisch konfigurierten Endpunkt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-135">You cannot use configuration to modify settings on the automatically-configured endpoint.</span></span> <span data-ttu-id="0c7c5-136">Muss eine Einstellung (etwa das Readerkontingent) geändert werden, dürfen Sie nicht den konfigurationsfreien Ansatz verwenden, indem Sie <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> aus der SVC-Datei entfernen und einen Konfigurationseintrag für den Endpunkt einfügen.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-136">If any setting (such as a reader quota) must be modified, you must not use the configuration-free approach by removing the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> from the .svc file and creating a configuration entry for the endpoint.</span></span>  
  
 <span data-ttu-id="0c7c5-137">Wenn Ihr Dienst den ASP.NET-Kompatibilitätsmodus erfordert &amp;#8211; etwa weil er die <xref:System.Web.HttpContext>-Klasse oder den ASP.NET-Autorisierungsmechanismus verwendet &amp;#8211; ist eine Konfigurationsdatei erforderlich, damit dieser Modus aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-137">If your service requires ASP.NET Compatibility Mode - for example, if it uses the <xref:System.Web.HttpContext> class or ASP.NET authorization mechanisms - a configuration file is still required to turn on this mode.</span></span> <span data-ttu-id="0c7c5-138">Das erforderliche Konfigurationselement ist die [ \<ServiceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) -Element, das wie folgt hinzugefügt werden muss.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-138">The configuration element required is the [\<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) element, which must be added as follows.</span></span>  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 <span data-ttu-id="0c7c5-139">Weitere Informationen finden Sie unter den [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-139">For more information, see the [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) topic.</span></span>  
  
 <span data-ttu-id="0c7c5-140">Bei der <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>-Klasse handelt es sich um eine abgeleitete Klasse von <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-140">The <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> class is a derived class of <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span></span> <span data-ttu-id="0c7c5-141">Eine ausführliche Erläuterung der Diensthostfactory-Mechanismus, finden Sie unter den [erweitern Hosting mithilfe von ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="0c7c5-141">For a detailed explanation of the service host factory mechanism, see the [Extending Hosting Using ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c7c5-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c7c5-142">See also</span></span>

- [<span data-ttu-id="0c7c5-143">Erstellen von WCF-Diensten für ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="0c7c5-143">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="0c7c5-144">Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF</span><span class="sxs-lookup"><span data-stu-id="0c7c5-144">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
