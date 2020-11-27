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
# <a name="wcf-web-http-formatting"></a>WCF-Web-http-Formatierung

Mit dem WCF-Web-HTTP-Programmiermodell können Sie dynamisch das beste Format für einen Dienstvorgang bestimmen, in dem dieser seine Antwort zurückgibt. Es werden zwei Methoden zum Bestimmen eines entsprechenden Formats unterstützt: automatisch und explizit.  
  
## <a name="automatic-formatting"></a>Automatische Formatierung  

 Wenn Sie aktiviert ist, wählt die automatische Formatierung das beste Format aus, in dem die Antwort zurückgegeben wird. Das beste Format wird bestimmt, indem Folgendes in der unten angegebenen Reihenfolge überprüft wird:  
  
1. Medientypen im Accept-Header der Anforderungsnachricht  
  
2. Inhaltstyp der Anforderungsnachricht  
  
3. Standardformateinstellung des Vorgangs  
  
4. Standardformateinstellung unter WebHttpBehavior  
  
 Wenn die Anforderungs Nachricht einen Accept-Header enthält, sucht die Windows Communication Foundation (WCF)-Infrastruktur nach einem Typ, der von ihr unterstützt wird. Wenn der `Accept`-Header Prioritäten für seine Medientypen angibt, werden diese beachtet. Wird im `Accept`-Header kein geeignetes Format gefunden, wird der Inhaltstyp der Anforderungsnachricht verwendet. Wird kein geeigneter Inhaltstyp angegeben, wird die Standardformateinstellung für den Vorgang verwendet. Das Standardformat wird mit dem `ResponseFormat`-Parameter der Attribute <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> festgelegt. Falls für den Vorgang kein Standardformat angegeben ist, wird der Wert der <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A>-Eigenschaft verwendet. Die automatische Formatierung verwendet die <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>-Eigenschaft. Wenn diese Eigenschaft auf `true` festgelegt wird, bestimmte die WCF-Infrastruktur das beste Format. Die automatische Formatauswahl ist standardmäßig deaktiviert, um die Abwärtskompatibilität sicherzustellen. Sie können die automatische Formatauswahl programmgesteuert oder per Konfiguration aktivieren. Im folgenden Beispiel wird gezeigt, wie Sie die automatische Formatauswahl im Code aktivieren.  
  
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
  
 Sie können die automatische Formatierung auch per Konfiguration aktivieren. Legen Sie dazu die <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>-Eigenschaft direkt unter <xref:System.ServiceModel.Description.WebHttpBehavior> festlegen oder <xref:System.ServiceModel.Description.WebHttpEndpoint> verwenden. Im folgenden Beispiel wird gezeigt, wie Sie die automatische Formatauswahl unter <xref:System.ServiceModel.Description.WebHttpBehavior> aktivieren.  
  
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
  
 Im folgenden Beispiel wird gezeigt, wie Sie die automatische Formatauswahl mithilfe von <xref:System.ServiceModel.Description.WebHttpEndpoint> aktivieren.  
  
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
  
## <a name="explicit-formatting"></a>Explizite Formatierung  

 Wie der Name bereits vermuten lässt, bestimmt bei der expliziten Formatierung der Entwickler das beste Format für die Verwendung im Vorgangscode. Falls das beste Format XML oder JSON ist, legt der Entwickler <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> auf <xref:System.ServiceModel.Web.WebMessageFormat.Xml> oder <xref:System.ServiceModel.Web.WebMessageFormat.Json> fest. Falls die <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>-Eigenschaft nicht explizit festgelegt wird, wird das Standardformat des Vorgangs verwendet.  
  
 Im folgenden Beispiel wird der Formatabfrage-Zeichenfolgenparameter für ein zu verwendendes Format überprüft. Wenn er angegeben wurde, wird das Format des Vorgangs mit <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> festgelegt.  
  
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
  
 Falls Sie andere Formate als XML oder JSON unterstützen müssen, definieren Sie für den Vorgang den Rückgabetyp <xref:System.ServiceModel.Channels.Message>. Bestimmen Sie innerhalb des Vorgangscodes das passende Format, und erstellen SIe dann ein <xref:System.ServiceModel.Channels.Message>-Objekt, indem Sie eine der folgenden Methoden verwenden:  
  
- `WebOperationContext.CreateAtom10Response`  
  
- `WebOperationContext.CreateJsonResponse`  
  
- `WebOperationContext.CreateStreamResponse`  
  
- `WebOperationContext.CreateTextResponse`  
  
- `WebOperationContext.CreateXmlResponse`  
  
 Jede dieser Methoden verwendet Inhalt und erstellt eine Nachricht im passenden Format. Sie können die `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements`-Methode verwenden, um eine Liste der vom Client bevorzugten Formate in der entsprechenden Reihenfolge abzurufen. Das folgende Beispiel zeigt, wie Sie `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` verwenden, um das Format zu bestimmen. Anschließend wird die entsprechende Methode zum Erstellen der Antwortnachricht verwendet.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.UriTemplate>
- <xref:System.UriTemplateMatch>
- [WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model.md)
- [UriTemplate und UriTemplateTable](uritemplate-and-uritemplatetable.md)
- [Überblick über WCF-Web-HTTP-Programmiermodelle](wcf-web-http-programming-model-overview.md)
- [Objektmodell für WCF-Web-HTTP-Programmierung](wcf-web-http-programming-object-model.md)
