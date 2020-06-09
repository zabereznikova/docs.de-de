---
title: 'Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration'
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 9aab53d6457aa7848fd4acea6317a30da352cc98
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579630"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a><span data-ttu-id="1a010-102">Vorgehensweise: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1a010-102">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>
<span data-ttu-id="1a010-103">Mit Windows Communication Foundation (WCF) können Sie einen Dienst erstellen, der einen ASP.NET AJAX-aktivierten Endpunkt verfügbar macht, der von JavaScript auf einer Client Website aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1a010-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="1a010-104">Zum Erstellen eines solchen Endpunkts können Sie entweder (wie bei allen anderen WCF-Endpunkten) eine Konfigurationsdatei verwenden, oder Sie können eine Methode einsetzen, die keine Konfigurationselemente benötigt.</span><span class="sxs-lookup"><span data-stu-id="1a010-104">To create such an endpoint, you can either use a configuration file, as with all other WCF endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="1a010-105">In diesem Thema wird die zweite Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1a010-105">This topic demonstrates the second approach.</span></span>  
  
 <span data-ttu-id="1a010-106">Um Dienste mit ASP.NET AJAX-Endpunkten ohne Konfiguration zu erstellen, müssen diese Dienste von Internetinformationsdiensten (IIS) gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="1a010-106">To create services with ASP.NET AJAX endpoints without configuration, the services must be hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="1a010-107">Um einen ASP.NET AJAX-Endpunkt mithilfe dieses Ansatzes zu aktivieren, geben Sie <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> als factoryparameter in der [ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive in der SVC-Datei an.</span><span class="sxs-lookup"><span data-stu-id="1a010-107">To activate an ASP.NET AJAX endpoint using this approach, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> as the Factory parameter in the [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive in the .svc file.</span></span> <span data-ttu-id="1a010-108">Diese benutzerdefinierte Factory ist die Komponente, die automatisch einen ASP.NET AJAX-Endpunkt konfiguriert, damit er auf einer Client-Website von JavaScript aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1a010-108">This custom factory is the component that automatically configures an ASP.NET AJAX endpoint so that it can be called from JavaScript on a client Web site.</span></span>  
  
 <span data-ttu-id="1a010-109">Ein funktionierendes Beispiel finden Sie unter [AJAX-Dienst ohne Konfiguration](../samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1a010-109">For a working example, see the [AJAX Service Without Configuration](../samples/ajax-service-without-configuration.md).</span></span>  
  
 <span data-ttu-id="1a010-110">Einen Überblick über die Konfiguration eines ASP.NET AJAX-Endpunkts mithilfe von Konfigurationselementen finden [Sie unter Gewusst wie: Hinzufügen eines ASP.NET AJAX-Endpunkts](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)mit der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="1a010-110">For an outline of how to configure an ASP.NET AJAX endpoint using configuration elements, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="1a010-111">So erstellen Sie einen WCF-Basisdienst</span><span class="sxs-lookup"><span data-stu-id="1a010-111">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="1a010-112">Definieren Sie einen grundlegenden WCF-Dienstvertrag mit einer mit dem-Attribut markierten Schnittstelle <xref:System.ServiceModel.ServiceContractAttribute> .</span><span class="sxs-lookup"><span data-stu-id="1a010-112">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="1a010-113">Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1a010-113">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="1a010-114">Stellen Sie sicher, dass Sie die <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="1a010-114">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
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
  
2. <span data-ttu-id="1a010-115">Implementieren Sie den `ICalculator`-Dienstvertrag mit `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="1a010-115">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. <span data-ttu-id="1a010-116">Definieren Sie einen Namespace für die `ICalculator`- und die `CalculatorService`-Implementierung, indem Sie sie in einen Namespaceblock einschließen.</span><span class="sxs-lookup"><span data-stu-id="1a010-116">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a><span data-ttu-id="1a010-117">So hosten Sie einen Dienst in Internetinformationsdiensten (IIS) ohne Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1a010-117">To host the service in Internet Information Services without configuration</span></span>  
  
1. <span data-ttu-id="1a010-118">Erstellen Sie eine neue Datei mit einer SVC-Erweiterung in der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1a010-118">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="1a010-119">Bearbeiten Sie diese Datei, indem Sie die entsprechenden [ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md) -Direktiveninformationen für den Dienst hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1a010-119">Edit this file by adding the appropriate [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="1a010-120">Geben Sie an, dass <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> in der [ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive verwendet werden soll, um einen ASP.NET AJAX-Endpunkt automatisch zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1a010-120">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. <span data-ttu-id="1a010-121">Erstellen Sie den Dienst, und rufen Sie ihn vom Client aus auf.</span><span class="sxs-lookup"><span data-stu-id="1a010-121">Build the service and call it from the client.</span></span> <span data-ttu-id="1a010-122">Internetinformationsdienste (IIS) aktiviert den Dienst, sobald er aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1a010-122">Internet Information Services (IIS) activates the service when called.</span></span> <span data-ttu-id="1a010-123">Weitere Informationen zum Hosten in IIS finden Sie unter Gewusst [wie: Hosten eines WCF-Diensts in IIS](how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="1a010-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="1a010-124">So rufen Sie den Dienst auf</span><span class="sxs-lookup"><span data-stu-id="1a010-124">To call the service</span></span>  
  
1. <span data-ttu-id="1a010-125">Der Endpunkt wird mit einer leeren Adresse relativ zur SVC-Datei konfiguriert, sodass der Dienst jetzt verfügbar ist und aufgerufen werden kann, indem Anforderungen an Service. svc gesendet werden, z. b. " \<operation> Service. svc/Add" für den `Add` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="1a010-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="1a010-126">Sie können ihn verwenden, indem Sie die Dienst-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben.</span><span class="sxs-lookup"><span data-stu-id="1a010-126">You can use it by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="1a010-127">Ein Beispiel finden Sie unter [AJAX-Dienst ohne Konfiguration](../samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1a010-127">For an example, see the [AJAX Service Without Configuration](../samples/ajax-service-without-configuration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a010-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a010-128">Example</span></span>  
  
 <span data-ttu-id="1a010-129">Der automatisch konfigurierte Endpunkt wird bei einer leeren Adresse relativ zur Basis-URL erstellt.</span><span class="sxs-lookup"><span data-stu-id="1a010-129">The automatically-configured endpoint is created at an empty address relative to the base URL.</span></span> <span data-ttu-id="1a010-130">Bei diesem Ansatz wird auch eine Konfigurationsdatei hinzugefügt und verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a010-130">A configuration file can also be added and used with this approach.</span></span> <span data-ttu-id="1a010-131">Wenn die Konfigurationsdatei Endpunktdefinitionen enthält, werden diese Endpunkte dem automatisch konfigurierten Endpunkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1a010-131">If the configuration file contains endpoint definitions, these endpoints are added to the automatically-configured endpoint.</span></span>  
  
 <span data-ttu-id="1a010-132">Die Datei "service.svc" verwendet beispielsweise die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, und das Dienstverzeichnis enthält eine Web.config-Datei, die mithilfe der <xref:System.ServiceModel.BasicHttpBinding> einen Endpunkt für den gleichen Dienst definiert, wobei für diesen eine zu "soap" relative Adresse angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="1a010-132">For example, service.svc uses the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> and the service directory contains a Web.config file that defines an endpoint for the same service using the <xref:System.ServiceModel.BasicHttpBinding> at the "soap" relative address.</span></span> <span data-ttu-id="1a010-133">In diesem Fall enthält der Dienst zwei Endpunkte: einen unter service.svc (der auf ASP.NET AJAX-Anforderungen antwortet) und einen weiteren unter service.svc/soap (der auf SOAP-Anforderungen antwortet).</span><span class="sxs-lookup"><span data-stu-id="1a010-133">In this case, the service contains two endpoints: one at service.svc (which responds to ASP.NET AJAX requests) and another at service.svc/soap (which responds to SOAP requests).</span></span>  
  
 <span data-ttu-id="1a010-134">Definiert die Konfigurationsdatei einen Endpunkt unter einer leeren relativen Adresse und wird <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> verwendet, wird eine Ausnahme ausgelöst, und der Start des Diensts schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="1a010-134">If the configuration file defines an endpoint at an empty relative address and the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used, an exception is thrown and the service fails to start.</span></span>  
  
 <span data-ttu-id="1a010-135">Sie können die Konfiguration nicht dazu verwenden, Einstellungen auf dem automatisch konfigurierten Endpunkt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1a010-135">You cannot use configuration to modify settings on the automatically-configured endpoint.</span></span> <span data-ttu-id="1a010-136">Muss eine Einstellung (etwa das Readerkontingent) geändert werden, dürfen Sie nicht den konfigurationsfreien Ansatz verwenden, indem Sie <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> aus der SVC-Datei entfernen und einen Konfigurationseintrag für den Endpunkt einfügen.</span><span class="sxs-lookup"><span data-stu-id="1a010-136">If any setting (such as a reader quota) must be modified, you must not use the configuration-free approach by removing the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> from the .svc file and creating a configuration entry for the endpoint.</span></span>  
  
 <span data-ttu-id="1a010-137">Wenn Ihr Dienst den ASP.NET-Kompatibilitätsmodus erfordert &#8211; etwa weil er die <xref:System.Web.HttpContext>-Klasse oder den ASP.NET-Autorisierungsmechanismus verwendet &#8211; ist eine Konfigurationsdatei erforderlich, damit dieser Modus aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1a010-137">If your service requires ASP.NET Compatibility Mode - for example, if it uses the <xref:System.Web.HttpContext> class or ASP.NET authorization mechanisms - a configuration file is still required to turn on this mode.</span></span> <span data-ttu-id="1a010-138">Das erforderliche Konfigurationselement ist das- [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) Element, das wie folgt hinzugefügt werden muss.</span><span class="sxs-lookup"><span data-stu-id="1a010-138">The configuration element required is the [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) element, which must be added as follows.</span></span>  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 <span data-ttu-id="1a010-139">Weitere Informationen finden Sie im Thema [WCF-Dienste und ASP.net](wcf-services-and-aspnet.md) .</span><span class="sxs-lookup"><span data-stu-id="1a010-139">For more information, see the [WCF Services and ASP.NET](wcf-services-and-aspnet.md) topic.</span></span>  
  
 <span data-ttu-id="1a010-140">Bei der <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>-Klasse handelt es sich um eine abgeleitete Klasse von <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="1a010-140">The <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> class is a derived class of <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span></span> <span data-ttu-id="1a010-141">Eine ausführliche Erläuterung des Diensthostfactory-Mechanismus finden Sie im Thema [Erweitern des Hosting mit ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md) .</span><span class="sxs-lookup"><span data-stu-id="1a010-141">For a detailed explanation of the service host factory mechanism, see the [Extending Hosting Using ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a010-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a010-142">See also</span></span>

- [<span data-ttu-id="1a010-143">Erstellen von WCF-Diensten für ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="1a010-143">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="1a010-144">Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF</span><span class="sxs-lookup"><span data-stu-id="1a010-144">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
