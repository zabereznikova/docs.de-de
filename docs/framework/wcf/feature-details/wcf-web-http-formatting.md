---
title: WCF-Web-http-Formatierung
ms.date: 03/30/2017
ms.assetid: e2414896-5463-41cd-b0a6-026a713eac2c
ms.openlocfilehash: e9346cd1bb3798ad0beac5e9e28a8536007d897b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266908"
---
# <a name="wcf-web-http-formatting"></a><span data-ttu-id="69ee7-102">WCF-Web-http-Formatierung</span><span class="sxs-lookup"><span data-stu-id="69ee7-102">WCF Web HTTP formatting</span></span>

<span data-ttu-id="69ee7-103">Mit dem WCF-Web-HTTP-Programmiermodell können Sie dynamisch das beste Format für einen Dienstvorgang bestimmen, in dem dieser seine Antwort zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="69ee7-103">The WCF Web HTTP programming model allows you to dynamically determine the best format for a service operation to return its response in.</span></span> <span data-ttu-id="69ee7-104">Es werden zwei Methoden zum Bestimmen eines entsprechenden Formats unterstützt: automatisch und explizit.</span><span class="sxs-lookup"><span data-stu-id="69ee7-104">Two methods for determining an appropriate format are supported: automatic and explicit.</span></span>  
  
## <a name="automatic-formatting"></a><span data-ttu-id="69ee7-105">Automatische Formatierung</span><span class="sxs-lookup"><span data-stu-id="69ee7-105">Automatic formatting</span></span>  

 <span data-ttu-id="69ee7-106">Wenn Sie aktiviert ist, wählt die automatische Formatierung das beste Format aus, in dem die Antwort zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="69ee7-106">When enabled, automatic formatting chooses the best format in which to return the response.</span></span> <span data-ttu-id="69ee7-107">Das beste Format wird bestimmt, indem Folgendes in der unten angegebenen Reihenfolge überprüft wird:</span><span class="sxs-lookup"><span data-stu-id="69ee7-107">It determines the best format by checking the following, in order:</span></span>  
  
1. <span data-ttu-id="69ee7-108">Medientypen im Accept-Header der Anforderungsnachricht</span><span class="sxs-lookup"><span data-stu-id="69ee7-108">The media types in the request message’s Accept header.</span></span>  
  
2. <span data-ttu-id="69ee7-109">Inhaltstyp der Anforderungsnachricht</span><span class="sxs-lookup"><span data-stu-id="69ee7-109">The content-type of the request message.</span></span>  
  
3. <span data-ttu-id="69ee7-110">Standardformateinstellung des Vorgangs</span><span class="sxs-lookup"><span data-stu-id="69ee7-110">The default format setting in the operation.</span></span>  
  
4. <span data-ttu-id="69ee7-111">Standardformateinstellung unter WebHttpBehavior</span><span class="sxs-lookup"><span data-stu-id="69ee7-111">The default format setting in the WebHttpBehavior.</span></span>  
  
 <span data-ttu-id="69ee7-112">Wenn die Anforderungs Nachricht einen Accept-Header enthält, sucht die Windows Communication Foundation (WCF)-Infrastruktur nach einem Typ, der von ihr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="69ee7-112">If the request message contains an Accept header the Windows Communication Foundation (WCF) infrastructure searches for a type that it supports.</span></span> <span data-ttu-id="69ee7-113">Wenn der `Accept`-Header Prioritäten für seine Medientypen angibt, werden diese beachtet.</span><span class="sxs-lookup"><span data-stu-id="69ee7-113">If the `Accept` header specifies priorities for its media types, they are honored.</span></span> <span data-ttu-id="69ee7-114">Wird im `Accept`-Header kein geeignetes Format gefunden, wird der Inhaltstyp der Anforderungsnachricht verwendet.</span><span class="sxs-lookup"><span data-stu-id="69ee7-114">If no suitable format is found in the `Accept` header, the content-type of the request message is used.</span></span> <span data-ttu-id="69ee7-115">Wird kein geeigneter Inhaltstyp angegeben, wird die Standardformateinstellung für den Vorgang verwendet.</span><span class="sxs-lookup"><span data-stu-id="69ee7-115">If no suitable content-type is specified, the default format setting for the operation is used.</span></span> <span data-ttu-id="69ee7-116">Das Standardformat wird mit dem `ResponseFormat`-Parameter der Attribute <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="69ee7-116">The default format is set with the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes.</span></span> <span data-ttu-id="69ee7-117">Falls für den Vorgang kein Standardformat angegeben ist, wird der Wert der <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A>-Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="69ee7-117">If no default format is specified on the operation, the value of the <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A> property is used.</span></span> <span data-ttu-id="69ee7-118">Die automatische Formatierung verwendet die <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="69ee7-118">Automatic formatting relies on the <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> property.</span></span> <span data-ttu-id="69ee7-119">Wenn diese Eigenschaft auf `true` festgelegt wird, bestimmte die WCF-Infrastruktur das beste Format.</span><span class="sxs-lookup"><span data-stu-id="69ee7-119">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="69ee7-120">Die automatische Formatauswahl ist standardmäßig deaktiviert, um die Abwärtskompatibilität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="69ee7-120">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="69ee7-121">Sie können die automatische Formatauswahl programmgesteuert oder per Konfiguration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="69ee7-121">Automatic format selection can be enabled programmatically or through configuration.</span></span> <span data-ttu-id="69ee7-122">Im folgenden Beispiel wird gezeigt, wie Sie die automatische Formatauswahl im Code aktivieren.</span><span class="sxs-lookup"><span data-stu-id="69ee7-122">The following example shows how to enable automatic format selection in code.</span></span>  
  
```csharp
// This code assumes the service name is MyService and the service contract is IMyContract
Uri baseAddress = new Uri("http://localhost:8000");  
  
WebServiceHost host = new WebServiceHost(typeof(MyService), baseAddress)  
try  
{  
   ServiceEndpoint sep = host.AddServiceEndpoint(typeof(IMyContract), new WebHttpBinding(), "");  
   // Check it see if the WebHttpBehavior already exists  
   WebHttpBehavior whb = sep.Behaviors.Find<WebHttpBehavior>();  
  
   if (whb != null)  
   {  
      whb.AutomaticFormatSelectionEnabled = true;  
   }  
   else  
   {  
      WebHttpBehavior webBehavior = new WebHttpBehavior();  
      webBehavior.AutomaticFormatSelectionEnabled = true;  
      sep.Behaviors.Add(webBehavior);  
   }  
         // Open host to start listening for messages  
   host.Open();
  
  // ...  
}  
  catch(CommunicationException ex)  
  {  
     Console.WriteLine("An exception occurred: " + ex.Message());  
  }  
```  
  
 <span data-ttu-id="69ee7-123">Sie können die automatische Formatierung auch per Konfiguration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="69ee7-123">Automatic formatting can also be enabled through configuration.</span></span> <span data-ttu-id="69ee7-124">Legen Sie dazu die <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>-Eigenschaft direkt unter <xref:System.ServiceModel.Description.WebHttpBehavior> festlegen oder <xref:System.ServiceModel.Description.WebHttpEndpoint> verwenden.</span><span class="sxs-lookup"><span data-stu-id="69ee7-124">You can set the <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> property directly on the <xref:System.ServiceModel.Description.WebHttpBehavior> or using the <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span></span> <span data-ttu-id="69ee7-125">Im folgenden Beispiel wird gezeigt, wie Sie die automatische Formatauswahl unter <xref:System.ServiceModel.Description.WebHttpBehavior> aktivieren.</span><span class="sxs-lookup"><span data-stu-id="69ee7-125">The following example shows how to enable the automatic format selection on the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <endpointBehaviors>  
      <behavior>  
        <webHttp automaticFormatSelectionEnabled="true" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- the "" standard endpoint is used by WebServiceHost for auto creating a web endpoint. -->  
      <standardEndpoint name="" helpEnabled="true" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="69ee7-126">Im folgenden Beispiel wird gezeigt, wie Sie die automatische Formatauswahl mithilfe von <xref:System.ServiceModel.Description.WebHttpEndpoint> aktivieren.</span><span class="sxs-lookup"><span data-stu-id="69ee7-126">The following example shows how to enable automatic format selection using <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>  
      <webHttpEndpoint>  
        <!-- the "" standard endpoint is used by WebServiceHost for auto creating a web endpoint. -->  
        <standardEndpoint name="" helpEnabled="true" automaticFormatSelectionEnabled="true"  />  
      </webHttpEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
```  
  
## <a name="explicit-formatting"></a><span data-ttu-id="69ee7-127">Explizite Formatierung</span><span class="sxs-lookup"><span data-stu-id="69ee7-127">Explicit formatting</span></span>  

 <span data-ttu-id="69ee7-128">Wie der Name bereits vermuten lässt, bestimmt bei der expliziten Formatierung der Entwickler das beste Format für die Verwendung im Vorgangscode.</span><span class="sxs-lookup"><span data-stu-id="69ee7-128">As the name implies, in explicit formatting the developer determines the best format to use within the operation code.</span></span> <span data-ttu-id="69ee7-129">Falls das beste Format XML oder JSON ist, legt der Entwickler <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> auf <xref:System.ServiceModel.Web.WebMessageFormat.Xml> oder <xref:System.ServiceModel.Web.WebMessageFormat.Json> fest.</span><span class="sxs-lookup"><span data-stu-id="69ee7-129">If the best format is XML or JSON the developer sets <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> to either <xref:System.ServiceModel.Web.WebMessageFormat.Xml> or <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="69ee7-130">Falls die <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>-Eigenschaft nicht explizit festgelegt wird, wird das Standardformat des Vorgangs verwendet.</span><span class="sxs-lookup"><span data-stu-id="69ee7-130">If the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property is not explicitly set, then the operation’s default format is used.</span></span>  
  
 <span data-ttu-id="69ee7-131">Im folgenden Beispiel wird der Formatabfrage-Zeichenfolgenparameter für ein zu verwendendes Format überprüft.</span><span class="sxs-lookup"><span data-stu-id="69ee7-131">The following example checks the format query string parameter for a format to use.</span></span> <span data-ttu-id="69ee7-132">Wenn er angegeben wurde, wird das Format des Vorgangs mit <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="69ee7-132">If it has been specified, it sets the operation’s format using <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>.</span></span>  
  
```csharp
public class Service : IService  
{  
    [WebGet]  
     public string EchoWithGet(string s)  
    {  
        // if a format query string parameter has been specified, set the response format to that. If no such
        // query string parameter exists the Accept header will be used
        string formatQueryStringValue = WebOperationContext.Current.IncomingRequest.UriTemplateMatch.QueryParameters["format"];  
        if (!string.IsNullOrEmpty(formatQueryStringValue))  
        {  
            if (formatQueryStringValue.Equals("xml", System.StringComparison.OrdinalIgnoreCase))  
            {
                WebOperationContext.Current.OutgoingResponse.Format = WebMessageFormat.Xml;
            }
            else if (formatQueryStringValue.Equals("json", System.StringComparison.OrdinalIgnoreCase))  
            {  
                WebOperationContext.Current.OutgoingResponse.Format = WebMessageFormat.Json;  
            }  
            else  
            {  
                throw new WebFaultException<string>($"Unsupported format '{formatQueryStringValue}'",   HttpStatusCode.BadRequest);
            }  
        }  
        return "You said " + s;  
    }  
```  
  
 <span data-ttu-id="69ee7-133">Falls Sie andere Formate als XML oder JSON unterstützen müssen, definieren Sie für den Vorgang den Rückgabetyp <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="69ee7-133">If you need to support formats other than XML or JSON, define your operation to have a return type of <xref:System.ServiceModel.Channels.Message>.</span></span> <span data-ttu-id="69ee7-134">Bestimmen Sie innerhalb des Vorgangscodes das passende Format, und erstellen SIe dann ein <xref:System.ServiceModel.Channels.Message>-Objekt, indem Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="69ee7-134">Within the operation code, determine the appropriate format to use and then create a <xref:System.ServiceModel.Channels.Message> object using one of the following methods:</span></span>  
  
- `WebOperationContext.CreateAtom10Response`  
  
- `WebOperationContext.CreateJsonResponse`  
  
- `WebOperationContext.CreateStreamResponse`  
  
- `WebOperationContext.CreateTextResponse`  
  
- `WebOperationContext.CreateXmlResponse`  
  
 <span data-ttu-id="69ee7-135">Jede dieser Methoden verwendet Inhalt und erstellt eine Nachricht im passenden Format.</span><span class="sxs-lookup"><span data-stu-id="69ee7-135">Each of these methods takes content and creates a message with the appropriate format.</span></span> <span data-ttu-id="69ee7-136">Sie können die `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements`-Methode verwenden, um eine Liste der vom Client bevorzugten Formate in der entsprechenden Reihenfolge abzurufen.</span><span class="sxs-lookup"><span data-stu-id="69ee7-136">The `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` method can be used to get a list of formats preferred by the client in order of decreasing preference.</span></span> <span data-ttu-id="69ee7-137">Das folgende Beispiel zeigt, wie Sie `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` verwenden, um das Format zu bestimmen. Anschließend wird die entsprechende Methode zum Erstellen der Antwortnachricht verwendet.</span><span class="sxs-lookup"><span data-stu-id="69ee7-137">The following example shows how to use `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` to determine the format to use and then uses the appropriate create response method to create the response message.</span></span>  
  
```csharp
public class Service : IService  
{  
    public Message EchoListWithGet(string list)  
    {  
        List<string> returnList = new List<string>(list.Split(new char[] { ',' }, StringSplitOptions.RemoveEmptyEntries));  
        IList<ContentType> acceptHeaderElements = WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements();  
        for (int x = 0; x < acceptHeaderElements.Count; x++)  
        {  
            string normalizedMediaType = acceptHeaderElements[x].MediaType.ToLowerInvariant();  
            switch (normalizedMediaType)  
            {  
                case "image/jpeg": return CreateJpegResponse(returnList);  
                case "application/xhtml+xml": return CreateXhtmlResponse(returnList);  
                case "application/atom+xml": return CreateAtom10Response(returnList);  
                case "application/xml": return CreateXmlResponse(returnList);  
                case "application/json": return CreateJsonResponse(returnList);  
          }  
    }  
  
    // Default response format is XML  
    return CreateXmlResponse(returnList);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="69ee7-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69ee7-138">See also</span></span>

- <xref:System.UriTemplate>
- <xref:System.UriTemplateMatch>
- [<span data-ttu-id="69ee7-139">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="69ee7-139">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- [<span data-ttu-id="69ee7-140">UriTemplate und UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="69ee7-140">UriTemplate and UriTemplateTable</span></span>](uritemplate-and-uritemplatetable.md)
- [<span data-ttu-id="69ee7-141">Überblick über WCF-Web-HTTP-Programmiermodelle</span><span class="sxs-lookup"><span data-stu-id="69ee7-141">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)
- [<span data-ttu-id="69ee7-142">Objektmodell für WCF-Web-HTTP-Programmierung</span><span class="sxs-lookup"><span data-stu-id="69ee7-142">WCF Web HTTP Programming Object Model</span></span>](wcf-web-http-programming-object-model.md)
