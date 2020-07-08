---
title: 'Vorgehensweise: Auswählen zwischen HTTP POST- und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte'
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: c74b1acdf3802ab680123cd9d676919fe47236e8
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051583"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a><span data-ttu-id="4129e-102">Vorgehensweise: Auswählen zwischen HTTP POST- und HTTP GET-Anforderungen für ASP.NET AJAX-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="4129e-102">How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints</span></span>

<span data-ttu-id="4129e-103">Mit Windows Communication Foundation (WCF) können Sie einen Dienst erstellen, der einen ASP.NET AJAX-aktivierten Endpunkt verfügbar macht, der von JavaScript auf einer Client Website aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4129e-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="4129e-104">Die grundlegenden Verfahren zum entwickeln solcher Dienste finden Sie unter Gewusst [wie: Verwenden der Konfiguration zum Hinzufügen eines ASP.NET AJAX-Endpunkts](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) und Gewusst [wie: Hinzufügen eines ASP.NET AJAX-Endpunkts ohne Verwendung der Konfiguration](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="4129e-104">The basic procedures for building such services is discussed in [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) and [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
 <span data-ttu-id="4129e-105">ASP.NET AJAX unterstützt Vorgänge, die HTTP POST- und HTTP GET-Verben verwenden, wobei HTTP POST der Standard ist.</span><span class="sxs-lookup"><span data-stu-id="4129e-105">ASP.NET AJAX supports operations that use the HTTP POST and HTTP GET verbs, with HTTP POST being the default.</span></span> <span data-ttu-id="4129e-106">Wenn Sie einen Vorgang erstellen, der keine Nebeneffekte hat und Daten zurückgibt, die sich selten oder niemals ändern, können Sie stattdessen HTTP GET verwenden.</span><span class="sxs-lookup"><span data-stu-id="4129e-106">When creating an operation that has no side effects and returns data that rarely or never changes, use HTTP GET instead.</span></span> <span data-ttu-id="4129e-107">Die Ergebnisse von GET-Vorgängen können zwischengespeichert werden, was bedeutet, dass mehrere Aufrufe des gleichen Vorgangs zu nur einer Anforderung an den Dienst zusammengefasst werden können.</span><span class="sxs-lookup"><span data-stu-id="4129e-107">Results of GET operations can be cached, which means that multiple calls to the same operation may result in only one request to your service.</span></span> <span data-ttu-id="4129e-108">Die Zwischenspeicherung erfolgt nicht von WCF, kann jedoch auf jeder Ebene erfolgen (im Browser eines Benutzers, auf einem Proxy Server und auf anderen Ebenen). Das Caching ist von Vorteil, wenn Sie die Leistung des Dienstanbieter steigern möchten, dies ist jedoch möglicherweise nicht akzeptabel, wenn sich Daten häufig ändern oder wenn der Vorgang eine Aktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="4129e-108">The caching is not done by WCF but can take place at any level (in a user's browser, on a proxy server, and other levels.) Caching is advantageous if you want to increase service performance, but may not be acceptable if data changes frequently or if the operation performs some action.</span></span>  
  
 <span data-ttu-id="4129e-109">Wenn Sie beispielsweise einen Dienst für die Verwaltung der Musikbibliothek eines Benutzers entwickeln, ist es für einen Vorgang, der auf der Basis des Albumtitels den Künstler ermittelt, sinnvoll, GET zu verwenden. Ein Vorgang jedoch, der ein Album in die Sammlung des Benutzers einfügt, muss POST verwenden.</span><span class="sxs-lookup"><span data-stu-id="4129e-109">For example, if you are designing service to manage a user's music library, an operation that looks up the artist based on an album's title benefits from using GET, but an operation that adds an album to the user's personal collection must use POST.</span></span>  
  
 <span data-ttu-id="4129e-110">Verwenden Sie zur Steuerung der Lebensdauer des Zwischenspeichers den <xref:System.ServiceModel.Web.OutgoingWebResponseContext>-Typ.</span><span class="sxs-lookup"><span data-stu-id="4129e-110">To control the lifetime of the cache, use the <xref:System.ServiceModel.Web.OutgoingWebResponseContext> type.</span></span> <span data-ttu-id="4129e-111">Wenn Sie beispielsweise einen Dienst entwickeln, der stündlich aktualisierte Wettervorhersagen zurückgibt, könnten Sie GET verwenden, jedoch die Lebensdauer des Zwischenspeichers auf eine Stunde oder weniger beschränken, damit die Benutzer des Diensts keine veralteten Daten erhalten.</span><span class="sxs-lookup"><span data-stu-id="4129e-111">For example, when designing a service that returns weather forecasts updated hourly, you would use GET but limit the cache duration to an hour or less to prevent the users of the service from accessing stale data.</span></span>  
  
 <span data-ttu-id="4129e-112">Wenn Sie auf Dienste von einer ASP.NET AJAX-Seite zugreifen, die das Skript-Manager-Steuerelement verwendet, ist es gleichgültig, ob der Vorgang GET oder POST verwendet &#8211; der Skript-Manager stellt sicher, dass der korrekte Anforderungstyp ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4129e-112">When using services from an ASP.NET AJAX page that use the Script Manager control, it makes no difference whether the operation uses GET or POST - the script manager mechanism ensures that the correct request type is issued.</span></span>  
  
 <span data-ttu-id="4129e-113">HTTP GET-Vorgänge verwenden alle von POST-Vorgängen unterstützten Eingabeparameter, einschließlich komplexer Datenvertragstypen.</span><span class="sxs-lookup"><span data-stu-id="4129e-113">HTTP GET operations use any input parameters supported by POST operations, including complex data contract types.</span></span> <span data-ttu-id="4129e-114">In den meisten Fällen ist es jedoch empfehlenswert, zu viele oder zu komplexe Parameter in GET-Vorgängen zu vermeiden, da sie die Effizienz der Zwischenspeicherung vermindern.</span><span class="sxs-lookup"><span data-stu-id="4129e-114">However, in most cases it is recommended to avoid too many parameters or parameters that are too complex in GET operations because it reduces caching efficiency.</span></span>  
  
 <span data-ttu-id="4129e-115">In diesem Thema wird gezeigt, wie zwischen GET und POST ausgewählt wird, indem den relevanten Vorgängen das <xref:System.ServiceModel.Web.WebGetAttribute>- oder das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut im Dienstvertrag hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4129e-115">This topic demonstrates how to select between GET and POST by adding the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to the relevant operations in the service contract.</span></span> <span data-ttu-id="4129e-116">Die anderen Schritte (zum implementieren, konfigurieren und Hosten des Diensts), die zum Ausführen des Diensts erforderlich sind, ähneln denen, die von einem beliebigen ASP.NET AJAX-Dienst in WCF verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4129e-116">The other steps (to implement, configure and host the service) that are required to get the service running are similar to those used by any ASP.NET AJAX service in WCF.</span></span>  
  
 <span data-ttu-id="4129e-117">Ein mit dem <xref:System.ServiceModel.Web.WebGetAttribute> markierter Vorgang verwendet immer eine GET-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4129e-117">An operation marked with the <xref:System.ServiceModel.Web.WebGetAttribute> always uses a GET request.</span></span> <span data-ttu-id="4129e-118">Ein mit dem <xref:System.ServiceModel.Web.WebInvokeAttribute> oder mit keinem der beiden Attribute markierter Vorgang verwendet eine POST-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4129e-118">An operation marked with the <xref:System.ServiceModel.Web.WebInvokeAttribute>, or not marked with any of the two attributes, uses a POST request.</span></span> <span data-ttu-id="4129e-119">Das <xref:System.ServiceModel.Web.WebInvokeAttribute> erlaubt über die <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>-Eigenschaft die Verwendung anderer HTTP-Verben als GET und POST (etwa PUT und DELETE).</span><span class="sxs-lookup"><span data-stu-id="4129e-119">The <xref:System.ServiceModel.Web.WebInvokeAttribute> allows the use of other HTTP verbs, other than GET and POST (such as PUT and DELETE) through the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> property.</span></span> <span data-ttu-id="4129e-120">Diese Verben werden jedoch von ASP.NET AJAX nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4129e-120">However, these verbs are not supported by ASP.NET AJAX.</span></span> <span data-ttu-id="4129e-121">Verwenden Sie die <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>-Eigenschaft nicht, wenn Sie vorhaben, den Dienst von ASP.NET-Seiten aus aufzurufen, die das Skript-Manager-Steuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="4129e-121">If you intend to use the service from ASP.NET pages using the Script Manager control, do not use the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> property.</span></span>  
  
 <span data-ttu-id="4129e-122">Ein funktionierendes Beispiel für den Wechsel zu Get finden Sie im Beispiel für den [grundlegenden AJAX-Dienst](../samples/basic-ajax-service.md) .</span><span class="sxs-lookup"><span data-stu-id="4129e-122">For a working example of switching to GET, see the [Basic AJAX Service](../samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="4129e-123">Ein Beispiel für die Verwendung von Post finden Sie im Beispiel für den [AJAX-Dienst mit HTTP Post](../samples/ajax-service-using-http-post.md) .</span><span class="sxs-lookup"><span data-stu-id="4129e-123">For a sample that uses POST, see the [AJAX Service Using HTTP POST](../samples/ajax-service-using-http-post.md) sample.</span></span>  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a><span data-ttu-id="4129e-124">So erstellen Sie einen WCF-Dienst, der auf HTTP GET- oder HTTP POST-Anforderungen reagiert</span><span class="sxs-lookup"><span data-stu-id="4129e-124">To create a WCF service that responds to HTTP GET or HTTP POST requests</span></span>
  
1. <span data-ttu-id="4129e-125">Definieren Sie einen grundlegenden WCF-Dienstvertrag mit einer mit dem-Attribut markierten Schnittstelle <xref:System.ServiceModel.ServiceContractAttribute> .</span><span class="sxs-lookup"><span data-stu-id="4129e-125">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="4129e-126">Markieren Sie jeden Vorgang mit <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4129e-126">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="4129e-127">Fügen Sie das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut hinzu, um festzulegen, dass ein Vorgang auf HTTP GET-Anforderungen reagieren sollte.</span><span class="sxs-lookup"><span data-stu-id="4129e-127">Add the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to stipulate that an operation should respond to HTTP GET requests.</span></span> <span data-ttu-id="4129e-128">Sie können auch das <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut hinzufügen, um explizit die Auswahl von HTTP POST festzulegen, oder Sie geben überhaupt kein Attribut an, wodurch standardmäßig HTTP POST verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4129e-128">You can also add the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute to explicitly specify HTTP POST, or not specify an attribute, which defaults to HTTP POST.</span></span>
  
    ```csharp
    [ServiceContract]  
    public interface IMusicService  
    {  
        //This operation uses a GET method.  
        [OperationContract]  
        [WebGet]  
        string LookUpArtist(string album);  
  
        //This operation will use a POST method.  
        [OperationContract]  
        [WebInvoke]  
        void AddAlbum(string user, string album);  
  
        //This operation will use POST method by default  
        //since nothing else is explicitly specified.  
        [OperationContract]  
        string[] GetAlbums(string user);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="4129e-129">Implementieren Sie den `IMusicService`-Dienstvertrag mit `MusicService`.</span><span class="sxs-lookup"><span data-stu-id="4129e-129">Implement the `IMusicService` service contract with a `MusicService`.</span></span>
  
    ```csharp
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3. <span data-ttu-id="4129e-130">Erstellen Sie eine neue Datei mit einer SVC-Erweiterung in der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4129e-130">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="4129e-131">Bearbeiten Sie diese Datei, indem Sie die entsprechenden [ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md) -Direktiveninformationen für den Dienst hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4129e-131">Edit this file by adding the appropriate [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="4129e-132">Geben Sie an, dass <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> in der [ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive verwendet werden soll, um einen ASP.NET AJAX-Endpunkt automatisch zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4129e-132">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```aspx-csharp
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a><span data-ttu-id="4129e-133">So rufen Sie den Dienst auf</span><span class="sxs-lookup"><span data-stu-id="4129e-133">To call the service</span></span>  
  
1. <span data-ttu-id="4129e-134">Sie können die GET-Vorgänge Ihres Diensts ohne irgendeinen Clientcode testen, indem Sie den Browser verwenden.</span><span class="sxs-lookup"><span data-stu-id="4129e-134">You can test your service's GET operations without any client code, by using the browser.</span></span> <span data-ttu-id="4129e-135">Wenn Ihr Dienst z. b. an der Adresse konfiguriert ist `http://example.com/service.svc` , wird `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` der Dienst von der Eingabe in die Adressleiste des Browsers aufgerufen und bewirkt, dass die Antwort heruntergeladen oder angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4129e-135">For example, if your service is configured at the `http://example.com/service.svc` address, then typing `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` into the browser address bar invokes the service and causes the response to be downloaded or displayed.</span></span>
  
2. <span data-ttu-id="4129e-136">Sie können Dienste mit GET-Vorgängen auf gleiche Weise wie jeden anderen ASP.NET AJAX-Dienst verwenden &#8211; indem Sie die Dienst-URL in die Scripts-Auflistung des ASP.NET AJAX Script Manager-Steuerelements eingeben.</span><span class="sxs-lookup"><span data-stu-id="4129e-136">You can use services with GET operations in the same way as any other ASP.NET AJAX services - by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="4129e-137">Ein Beispiel finden Sie unter [grundlegender AJAX-Dienst](../samples/basic-ajax-service.md).</span><span class="sxs-lookup"><span data-stu-id="4129e-137">For an example, see the [Basic AJAX Service](../samples/basic-ajax-service.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4129e-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4129e-138">See also</span></span>

- [<span data-ttu-id="4129e-139">Erstellen von WCF-Diensten für ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="4129e-139">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="4129e-140">Vorgehensweise: Migrieren AJAX-aktivierter ASP.NET-Webdienste nach WCF</span><span class="sxs-lookup"><span data-stu-id="4129e-140">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
