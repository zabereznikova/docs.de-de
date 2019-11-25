---
title: 'Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts'
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 3ccfb34614707c17885da3ed37f545bbab808869
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978266"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a><span data-ttu-id="13037-102">Vorgehensweise: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts</span><span class="sxs-lookup"><span data-stu-id="13037-102">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>
<span data-ttu-id="13037-103">Mit Windows Communication Foundation (WCF) können Sie einen Dienst erstellen, der einen ASP.NET AJAX-fähigen Endpunkt zur Verfügung stellt, der von JavaScript auf einer Client Website aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="13037-103">Windows Communication Foundation (WCF) allows you to create a service that makes an ASP.NET AJAX-enabled endpoint available that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="13037-104">Zum Erstellen eines solchen Endpunkts können Sie entweder eine Konfigurationsdatei wie alle anderen Windows Communication Foundation (WCF)-Endpunkte verwenden oder eine Methode verwenden, die keine Konfigurationselemente erfordert.</span><span class="sxs-lookup"><span data-stu-id="13037-104">To create such an endpoint, you can either use a configuration file, as with all other Windows Communication Foundation (WCF) endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="13037-105">In diesem Thema wird die Konfigurationsmethode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="13037-105">This topic demonstrates the configuration approach.</span></span>  
  
 <span data-ttu-id="13037-106">Der Teil der Prozedur, mit dem der Dienst Endpunkt ASP.NET AJAX-fähig werden kann, besteht aus der Konfiguration des Endpunkts für die Verwendung des <xref:System.ServiceModel.WebHttpBinding> und dem Hinzufügen des [\<enableWebScript->](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) Endpunkt Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="13037-106">The part of the procedure that enables the service endpoint to become ASP.NET AJAX-enabled consists of configuring the endpoint to use the <xref:System.ServiceModel.WebHttpBinding> and to add the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) endpoint behavior.</span></span> <span data-ttu-id="13037-107">Nach der Konfiguration des Endpunkts sind die Schritte zum Implementieren und Hosten des Diensts mit denen vergleichbar, die von einem beliebigen WCF-Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13037-107">After configuring the endpoint, the steps to implement and host the service are similar to those used by any WCF service.</span></span> <span data-ttu-id="13037-108">Ein funktionierendes Beispiel finden [Sie unter AJAX-Dienst mit HTTP Post](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="13037-108">For a working example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
 <span data-ttu-id="13037-109">Weitere Informationen zum Konfigurieren eines ASP.NET AJAX-Endpunkts ohne Verwendung der Konfiguration finden Sie unter Gewusst [wie: Hinzufügen eines ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)-Endpunkts ohne Verwendung der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="13037-109">For more information about how to configure an ASP.NET AJAX endpoint without using configuration, see [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
## <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="13037-110">So erstellen Sie einen WCF-Basisdienst</span><span class="sxs-lookup"><span data-stu-id="13037-110">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="13037-111">Definieren Sie einen einfachen WCF-Dienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.ServiceContractAttribute>-Attribut gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="13037-111">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="13037-112">Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="13037-112">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="13037-113">Stellen Sie sicher, dass Sie die <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="13037-113">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```csharp
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="13037-114">Implementieren Sie den `ICalculator`-Dienstvertrag mit `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="13037-114">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }
        // Other operations omitted…
    }
    ```  
  
3. <span data-ttu-id="13037-115">Definieren Sie einen Namespace für die `ICalculator`- und die `CalculatorService`-Implementierung, indem Sie sie in einen Namespaceblock einschließen.</span><span class="sxs-lookup"><span data-stu-id="13037-115">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp
    namespace Microsoft.Ajax.Samples
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
## <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a><span data-ttu-id="13037-116">So erstellen Sie einen ASP.NET AJAX-Endpunkt für den Dienst</span><span class="sxs-lookup"><span data-stu-id="13037-116">To create an ASP.NET AJAX endpoint for the service</span></span>  
  
1. <span data-ttu-id="13037-117">Erstellen Sie eine Verhaltens Konfiguration, und geben Sie das [\<enableWebScript->](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) Verhalten für ASP.NET AJAX-aktivierte Endpunkte des Dienstanbieter an.</span><span class="sxs-lookup"><span data-stu-id="13037-117">Create a behavior configuration and specify the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior for ASP.NET AJAX-enabled endpoints of the service.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="AspNetAjaxBehavior">  
                    <enableWebScript />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
    </system.serviceModel>  
    ```  
  
2. <span data-ttu-id="13037-118">Erstellen Sie einen Endpunkt für den Dienst, der <xref:System.ServiceModel.WebHttpBinding> und das ASP.NET AJAX-Verhalten verwendet, das im vorherigen Schritt definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="13037-118">Create an endpoint for the service that uses the <xref:System.ServiceModel.WebHttpBinding> and the ASP.NET AJAX behavior defined in the previous step.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <services>  
            <service name="Microsoft.Ajax.Samples.CalculatorService">  
                <endpoint address=""  
                    behaviorConfiguration="AspNetAjaxBehavior"   
                    binding="webHttpBinding"  
                    contract="Microsoft.Ajax.Samples.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>   
    ```  
  
## <a name="to-host-the-service-in-iis"></a><span data-ttu-id="13037-119">So hosten Sie den Dienst in IIS</span><span class="sxs-lookup"><span data-stu-id="13037-119">To host the service in IIS</span></span>  
  
1. <span data-ttu-id="13037-120">Um den Dienst in IIS zu hosten, erstellen Sie in der Anwendung eine neue Datei mit dem Namen service und einer SVC-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="13037-120">To host the service in IIS, create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="13037-121">Bearbeiten Sie diese Datei, indem Sie die entsprechenden [\@Service Host](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -Direktiveninformationen für den Dienst hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="13037-121">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="13037-122">Die Dienstdatei für das `CalculatorService`-Beispiel enthält z.&#160;B. folgende Informationen.</span><span class="sxs-lookup"><span data-stu-id="13037-122">For example, the content in the service file for the `CalculatorService` sample contains the following information.</span></span>  
  
    ```
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. <span data-ttu-id="13037-123">Weitere Informationen zum Hosten in IIS finden Sie unter Gewusst [wie: Hosten eines WCF-Diensts in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="13037-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
## <a name="to-call-the-service"></a><span data-ttu-id="13037-124">So rufen Sie den Dienst auf</span><span class="sxs-lookup"><span data-stu-id="13037-124">To call the service</span></span>  
  
1. <span data-ttu-id="13037-125">Der Endpunkt wird mit einer leeren Adresse relativ zur SVC-Datei konfiguriert, sodass der Dienst jetzt verfügbar ist und aufgerufen werden kann, indem Anforderungen an den Dienst. svc/\<Vorgang gesendet werden > z. b. "Service. svc/Add" für den `Add` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="13037-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="13037-126">Sie können ihn verwenden, indem Sie die Endpunkt-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben.</span><span class="sxs-lookup"><span data-stu-id="13037-126">You can use it by entering the endpoint URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="13037-127">Ein Beispiel finden Sie unter der [AJAX-Dienst mit HTTP Post](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="13037-127">For an example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13037-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13037-128">See also</span></span>

- [<span data-ttu-id="13037-129">Erstellen von WCF-Diensten für ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="13037-129">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="13037-130">Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste zu WCF</span><span class="sxs-lookup"><span data-stu-id="13037-130">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
