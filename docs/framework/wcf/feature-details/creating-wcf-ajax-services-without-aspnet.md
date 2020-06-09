---
title: Erstellen von WCF AJAX-Diensten ohne ASP.NET
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: b5f0f730f90227dcccc7e5ebf533d80a28f6e6eb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599294"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a><span data-ttu-id="c34b9-102">Erstellen von WCF AJAX-Diensten ohne ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c34b9-102">Creating WCF AJAX Services without ASP.NET</span></span>
<span data-ttu-id="c34b9-103">Auf Windows Communication Foundation (WCF) AJAX-Dienste kann von jeder JavaScript-aktivierten Webseite zugegriffen werden, ohne dass ASP.NET AJAX erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c34b9-103">Windows Communication Foundation (WCF) AJAX services can be accessed from any JavaScript-enabled Web page, without requiring ASP.NET AJAX.</span></span> <span data-ttu-id="c34b9-104">In diesem Thema wird beschrieben, wie ein solcher WCF-Dienst erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c34b9-104">This topic describes how to create such a WCF service.</span></span>  
  
 <span data-ttu-id="c34b9-105">Anweisungen zur Verwendung von WCF mit ASP.NET AJAX finden Sie unter [Erstellen von WCF-Diensten für ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md).</span><span class="sxs-lookup"><span data-stu-id="c34b9-105">For instructions on using WCF with ASP.NET AJAX, see [Creating WCF Services for ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md).</span></span>  
  
 <span data-ttu-id="c34b9-106">Die Erstellung eines WCF AJAX-Dienstanbieter besteht aus drei Teilen:</span><span class="sxs-lookup"><span data-stu-id="c34b9-106">There are three parts to a creating a WCF AJAX service:</span></span>  
  
- <span data-ttu-id="c34b9-107">Erstellen eines AJAX-Endpunkts, auf den vom Browser aus zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c34b9-107">Creating an AJAX endpoint that can be accessed from the browser.</span></span>  
  
- <span data-ttu-id="c34b9-108">Erstellen eines AJAX-kompatiblen Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="c34b9-108">Creating an AJAX-compatible service contract.</span></span>  
  
- <span data-ttu-id="c34b9-109">Zugreifen auf den WCF AJAX-Dienst.</span><span class="sxs-lookup"><span data-stu-id="c34b9-109">Accessing WCF AJAX services.</span></span>  
  
## <a name="creating-an-ajax-endpoint"></a><span data-ttu-id="c34b9-110">Erstellen eines AJAX-Endpunkts</span><span class="sxs-lookup"><span data-stu-id="c34b9-110">Creating an AJAX Endpoint</span></span>  
 <span data-ttu-id="c34b9-111">Die einfachste Möglichkeit, die AJAX-Unterstützung in einem WCF-Dienst zu aktivieren, ist die Verwendung der <xref:System.ServiceModel.Activation.WebServiceHostFactory> in der SVC-Datei, die dem Dienst zugeordnet ist, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c34b9-111">The most basic way to enable AJAX support in a WCF service is to use the <xref:System.ServiceModel.Activation.WebServiceHostFactory> in the .svc file associated with the service, as in the following example.</span></span>  
  
```text
<%ServiceHost
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 <span data-ttu-id="c34b9-112">Alternativ können Sie auch die Konfiguration verwenden, um einen AJAX-Endpunkt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c34b9-112">Alternatively, you can also use configuration to add an AJAX endpoint.</span></span> <span data-ttu-id="c34b9-113">Verwenden Sie die <xref:System.ServiceModel.WebHttpBinding> des Dienstendpunkts, und konfigurieren Sie diesen Endpunkt mit dem <xref:System.ServiceModel.Description.WebHttpBehavior>, wie im folgenden Codeausschnitt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c34b9-113">Use the <xref:System.ServiceModel.WebHttpBinding> on the service endpoint and configure that endpoint with the <xref:System.ServiceModel.Description.WebHttpBehavior> as shown in the following code snippet.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="AjaxBehavior">  
          <webHttp/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Ajax.Samples.CityService">  
        <endpoint
          address="ajaxEndpoint"  
          behaviorConfiguration="AjaxBehavior"  
          binding="webHttpBinding"  
          contract="Microsoft.Ajax.Samples.ICityService" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="c34b9-114">Ein funktionierendes Beispiel finden Sie unter [AJAX-Dienst mit JSON und XML](../samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="c34b9-114">For a working example, see the [AJAX Service with JSON and XML](../samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="creating-an-ajax-compatible-service-contract"></a><span data-ttu-id="c34b9-115">Erstellen eines AJAX-kompatiblen Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="c34b9-115">Creating an AJAX-Compatible Service Contract</span></span>  
 <span data-ttu-id="c34b9-116">Standardmäßig geben die über einem AJAX-Endpunkt verfügbar gemachten Dienstverträge Daten im XML-Format zurück.</span><span class="sxs-lookup"><span data-stu-id="c34b9-116">By default, service contracts exposed over an AJAX endpoint return data in the XML format.</span></span> <span data-ttu-id="c34b9-117">Ebenso standardmäßig kann auf die Dienstvorgänge über HTTP POST-Anforderungen mit URLs zugegriffen werden, die die Endpunktadresse gefolgt vom Vorgangsnamen enthalten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c34b9-117">Also, by default service operations are accessible through HTTP POST requests to URLs that include the endpoint address followed by the operation name, as shown in the following example.</span></span>  
  
```csharp
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 <span data-ttu-id="c34b9-118">Auf diesen Vorgang kann über HTTP Post an `http://serviceaddress/endpointaddress/GetCities` und eine XML-Nachricht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c34b9-118">This operation is accessible using an HTTP POST to `http://serviceaddress/endpointaddress/GetCities` and return an XML message.</span></span>  
  
 <span data-ttu-id="c34b9-119">Sie können das vollständige Webprogrammiermodell verwenden, um diese grundlegenden Aspekte anzupassen.</span><span class="sxs-lookup"><span data-stu-id="c34b9-119">You can use the full Web Programming Model to customize these basic aspects.</span></span> <span data-ttu-id="c34b9-120">Sie können beispielsweise die Attribute <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> verwenden, um zu steuern, auf welche HTTP-Verben der Vorgang reagiert, oder die Eigenschaft `UriTemplate` dieser jeweiligen Attribute verwenden, um benutzerdefinierte URIs anzugeben usw.</span><span class="sxs-lookup"><span data-stu-id="c34b9-120">For example, you can use the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to control the HTTP verb to which the operation responds or use the `UriTemplate` property of these respective attributes to specify custom URIs.</span></span> <span data-ttu-id="c34b9-121">Weitere Informationen finden Sie im Thema [WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model.md) .</span><span class="sxs-lookup"><span data-stu-id="c34b9-121">For more information, see the [WCF Web HTTP Programming Model](wcf-web-http-programming-model.md) topic.</span></span>  
  
 <span data-ttu-id="c34b9-122">Das JSON-Datenformat wird oft in AJAX-Diensten verwendet.</span><span class="sxs-lookup"><span data-stu-id="c34b9-122">The JSON data format is often used in AJAX services.</span></span> <span data-ttu-id="c34b9-123">Um einen Vorgang zu erstellen, der JSON statt XML zurückgibt, legen Sie die <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A>-Eigenschaft (oder die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>-Eigenschaft) auf <xref:System.ServiceModel.Web.WebMessageFormat.Json> fest.</span><span class="sxs-lookup"><span data-stu-id="c34b9-123">To create an operation that returns JSON instead of XML, set the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (or the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) property to <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="c34b9-124">Das Thema zur [eigenständigen JSON-Serialisierung](stand-alone-json-serialization.md) zeigt, wie integrierte .NET-Typen und Daten Vertragstypen JSON zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c34b9-124">The [Stand-Alone JSON Serialization](stand-alone-json-serialization.md) topic shows how built-in .NET types and data contract types map to JSON.</span></span>  
  
 <span data-ttu-id="c34b9-125">Normalerweise bestehen JSON-Anforderungen und -Antworten aus nur einem Element.</span><span class="sxs-lookup"><span data-stu-id="c34b9-125">Normally, JSON requests and responses consist of just one item.</span></span> <span data-ttu-id="c34b9-126">Für den vorangehenden `GetCities`-Vorgang ähnelt die Anforderung der folgenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c34b9-126">For the preceding `GetCities` operation, the request resembles the following statement.</span></span>  
  
```json
"na"  
```  
  
 <span data-ttu-id="c34b9-127">Die Antwort auf diese Anforderung ähnelt der folgenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c34b9-127">The response to that request resembles the following statement.</span></span>  
  
```json
["Nairobi", "Naples", "Nashville"]  
```  
  
 <span data-ttu-id="c34b9-128">Wenn der Vorgang einen zusätzlichen Parameter annimmt, muss der Anforderungsstil auf "wrapped" festgelegt werden, damit beide Parameter einem einzigen JSON-Objekt zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c34b9-128">If the operation takes an extra parameter, the request style must be wrapped to wrap both parameters in a single JSON object.</span></span> <span data-ttu-id="c34b9-129">Ein Beispiel für eine JSON-Nachricht in diesem Stil finden Sie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c34b9-129">An example of this style JSON message is in the following example.</span></span>  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 <span data-ttu-id="c34b9-130">Der folgende Vertrag akzeptiert diese Nachricht.</span><span class="sxs-lookup"><span data-stu-id="c34b9-130">The following contract accepts this message.</span></span>  
  
```csharp
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a><span data-ttu-id="c34b9-131">Zugreifen auf AJAX-Dienste</span><span class="sxs-lookup"><span data-stu-id="c34b9-131">Accessing AJAX Services</span></span>  
 <span data-ttu-id="c34b9-132">WCF AJAX-Endpunkte akzeptieren immer sowohl JSON-als auch XML-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="c34b9-132">WCF AJAX endpoints always accept both JSON and XML requests.</span></span>  
  
 <span data-ttu-id="c34b9-133">HTTP POST-Anforderungen mit dem Inhaltstyp "application/json" werden als JSON behandelt, und diejenigen mit Inhaltstyp, die XML angeben (z. b. "Text/XML") werden als XML behandelt.</span><span class="sxs-lookup"><span data-stu-id="c34b9-133">HTTP POST requests with a content-type of "application/json" are treated as JSON, and those with content-type that indicate XML (for example, "text/xml") are treated as XML.</span></span>  
  
 <span data-ttu-id="c34b9-134">HTTP GET-Anforderungen enthalten alle Anforderungsparameter in der URL selbst.</span><span class="sxs-lookup"><span data-stu-id="c34b9-134">HTTP GET requests contain all the request parameters in the URL itself.</span></span>  
  
 <span data-ttu-id="c34b9-135">Es obliegt dem Benutzer zu entscheiden, wie die HTTP-Anforderung für den Endpunkt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c34b9-135">It is up to the user to decide how to create the HTTP request to the endpoint.</span></span> <span data-ttu-id="c34b9-136">Der Benutzer kann umfassend steuern, wie das den Text der Anforderung bildende JSON erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c34b9-136">Also, the user has full control over constructing the JSON that forms the body of the request.</span></span> <span data-ttu-id="c34b9-137">Ein Beispiel für das Erstellen einer Anforderung aus JavaScript finden Sie unter [AJAX-Dienst mit JSON und XML](../samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="c34b9-137">For an example of creating a request from JavaScript, see the [AJAX Service with JSON and XML](../samples/ajax-service-with-json-and-xml-sample.md).</span></span>
