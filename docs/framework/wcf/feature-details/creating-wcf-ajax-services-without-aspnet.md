---
title: Erstellen von WCF AJAX-Diensten ohne ASP.NET
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: de7e5dc075a821518928514be532ea1940c1ff17
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627120"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a><span data-ttu-id="be73a-102">Erstellen von WCF AJAX-Diensten ohne ASP.NET</span><span class="sxs-lookup"><span data-stu-id="be73a-102">Creating WCF AJAX Services without ASP.NET</span></span>
<span data-ttu-id="be73a-103">Windows Communication Foundation (WCF)-AJAX-Dienste können von jeder JavaScript-aktivierten Webseite zugegriffen werden, ohne dass ASP.NET AJAX erforderlich wäre.</span><span class="sxs-lookup"><span data-stu-id="be73a-103">Windows Communication Foundation (WCF) AJAX services can be accessed from any JavaScript-enabled Web page, without requiring ASP.NET AJAX.</span></span> <span data-ttu-id="be73a-104">Dieses Thema beschreibt, wie ein solcher WCF-Dienst erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="be73a-104">This topic describes how to create such a WCF service.</span></span>  
  
 <span data-ttu-id="be73a-105">Anweisungen zum Verwenden von WCF mit ASP.NET AJAX finden Sie [Erstellen von WCF-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).</span><span class="sxs-lookup"><span data-stu-id="be73a-105">For instructions on using WCF with ASP.NET AJAX, see [Creating WCF Services for ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).</span></span>  
  
 <span data-ttu-id="be73a-106">Es gibt drei Teile, die zur Erstellung eines WCF AJAX-Diensts:</span><span class="sxs-lookup"><span data-stu-id="be73a-106">There are three parts to a creating a WCF AJAX service:</span></span>  
  
- <span data-ttu-id="be73a-107">Erstellen eines AJAX-Endpunkts, auf den vom Browser aus zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="be73a-107">Creating an AJAX endpoint that can be accessed from the browser.</span></span>  
  
- <span data-ttu-id="be73a-108">Erstellen eines AJAX-kompatiblen Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="be73a-108">Creating an AJAX-compatible service contract.</span></span>  
  
- <span data-ttu-id="be73a-109">Zugreifen auf den WCF AJAX-Dienst.</span><span class="sxs-lookup"><span data-stu-id="be73a-109">Accessing WCF AJAX services.</span></span>  
  
## <a name="creating-an-ajax-endpoint"></a><span data-ttu-id="be73a-110">Erstellen eines AJAX-Endpunkts</span><span class="sxs-lookup"><span data-stu-id="be73a-110">Creating an AJAX Endpoint</span></span>  
 <span data-ttu-id="be73a-111">Die einfachste Möglichkeit zum Aktivieren von AJAX-Unterstützung in einem WCF-Dienst ist die Verwendung der <xref:System.ServiceModel.Activation.WebServiceHostFactory> in der SVC-Datei, die Verbindung mit dem Dienst, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="be73a-111">The most basic way to enable AJAX support in a WCF service is to use the <xref:System.ServiceModel.Activation.WebServiceHostFactory> in the .svc file associated with the service, as in the following example.</span></span>  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 <span data-ttu-id="be73a-112">Alternativ können Sie auch die Konfiguration verwenden, um einen AJAX-Endpunkt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="be73a-112">Alternatively, you can also use configuration to add an AJAX endpoint.</span></span> <span data-ttu-id="be73a-113">Verwenden Sie die <xref:System.ServiceModel.WebHttpBinding> des Dienstendpunkts, und konfigurieren Sie diesen Endpunkt mit dem <xref:System.ServiceModel.Description.WebHttpBehavior>, wie im folgenden Codeausschnitt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="be73a-113">Use the <xref:System.ServiceModel.WebHttpBinding> on the service endpoint and configure that endpoint with the <xref:System.ServiceModel.Description.WebHttpBehavior> as shown in the following code snippet.</span></span>  
  
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
  
 <span data-ttu-id="be73a-114">Ein Arbeitsbeispiel finden Sie unter den [AJAX-Dienst mit JSON und XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="be73a-114">For a working example, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="creating-an-ajax-compatible-service-contract"></a><span data-ttu-id="be73a-115">Erstellen eines AJAX-kompatiblen Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="be73a-115">Creating an AJAX-Compatible Service Contract</span></span>  
 <span data-ttu-id="be73a-116">Standardmäßig geben die über einem AJAX-Endpunkt verfügbar gemachten Dienstverträge Daten im XML-Format zurück.</span><span class="sxs-lookup"><span data-stu-id="be73a-116">By default, service contracts exposed over an AJAX endpoint return data in the XML format.</span></span> <span data-ttu-id="be73a-117">Ebenso standardmäßig kann auf die Dienstvorgänge über HTTP POST-Anforderungen mit URLs zugegriffen werden, die die Endpunktadresse gefolgt vom Vorgangsnamen enthalten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="be73a-117">Also, by default service operations are accessible through HTTP POST requests to URLs that include the endpoint address followed by the operation name, as shown in the following example.</span></span>  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 <span data-ttu-id="be73a-118">Dieser Vorgang kann zugegriffen werden, mithilfe von HTTP POST für `http://serviceaddress/endpointaddress/GetCities` und zurückgeben eine XML-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="be73a-118">This operation is accessible using an HTTP POST to `http://serviceaddress/endpointaddress/GetCities` and return an XML message.</span></span>  
  
 <span data-ttu-id="be73a-119">Sie können das vollständige Webprogrammiermodell verwenden, um diese grundlegenden Aspekte anzupassen.</span><span class="sxs-lookup"><span data-stu-id="be73a-119">You can use the full Web Programming Model to customize these basic aspects.</span></span> <span data-ttu-id="be73a-120">Sie können beispielsweise die Attribute <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> verwenden, um zu steuern, auf welche HTTP-Verben der Vorgang reagiert, oder die Eigenschaft `UriTemplate` dieser jeweiligen Attribute verwenden, um benutzerdefinierte URIs anzugeben usw.</span><span class="sxs-lookup"><span data-stu-id="be73a-120">For example, you can use the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to control the HTTP verb to which the operation responds or use the `UriTemplate` property of these respective attributes to specify custom URIs.</span></span> <span data-ttu-id="be73a-121">Weitere Informationen finden Sie unter den [WCF-HTTP-Webprogrammierungsmodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="be73a-121">For more information, see the [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) topic.</span></span>  
  
 <span data-ttu-id="be73a-122">Das JSON-Datenformat wird oft in AJAX-Diensten verwendet.</span><span class="sxs-lookup"><span data-stu-id="be73a-122">The JSON data format is often used in AJAX services.</span></span> <span data-ttu-id="be73a-123">Um einen Vorgang zu erstellen, der JSON statt XML zurückgibt, legen Sie die <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A>-Eigenschaft (oder die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>-Eigenschaft) auf <xref:System.ServiceModel.Web.WebMessageFormat.Json> fest.</span><span class="sxs-lookup"><span data-stu-id="be73a-123">To create an operation that returns JSON instead of XML, set the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (or the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) property to <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="be73a-124">Die [eigenständige JSON-Serialisierung](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) Thema zeigt, wie die integrierten .NET Datentypen und Vertrag zugeordnet in JSON.</span><span class="sxs-lookup"><span data-stu-id="be73a-124">The [Stand-Alone JSON Serialization](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) topic shows how built-in .NET types and data contract types map to JSON.</span></span>  
  
 <span data-ttu-id="be73a-125">Normalerweise bestehen JSON-Anforderungen und -Antworten aus nur einem Element.</span><span class="sxs-lookup"><span data-stu-id="be73a-125">Normally, JSON requests and responses consist of just one item.</span></span> <span data-ttu-id="be73a-126">Für den vorangehenden `GetCities`-Vorgang ähnelt die Anforderung der folgenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="be73a-126">For the preceding `GetCities` operation, the request resembles the following statement.</span></span>  
  
```  
"na"  
```  
  
 <span data-ttu-id="be73a-127">Die Antwort auf diese Anforderung ähnelt der folgenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="be73a-127">The response to that request resembles the following statement.</span></span>  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 <span data-ttu-id="be73a-128">Wenn der Vorgang einen zusätzlichen Parameter annimmt, muss der Anforderungsstil auf "wrapped" festgelegt werden, damit beide Parameter einem einzigen JSON-Objekt zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="be73a-128">If the operation takes an extra parameter, the request style must be wrapped to wrap both parameters in a single JSON object.</span></span> <span data-ttu-id="be73a-129">Ein Beispiel für eine JSON-Nachricht in diesem Stil finden Sie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="be73a-129">An example of this style JSON message is in the following example.</span></span>  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 <span data-ttu-id="be73a-130">Der folgende Vertrag akzeptiert diese Nachricht.</span><span class="sxs-lookup"><span data-stu-id="be73a-130">The following contract accepts this message.</span></span>  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a><span data-ttu-id="be73a-131">Zugreifen auf AJAX-Dienste</span><span class="sxs-lookup"><span data-stu-id="be73a-131">Accessing AJAX Services</span></span>  
 <span data-ttu-id="be73a-132">WCF AJAX-Endpunkte akzeptieren immer sowohl JSON- und XML-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="be73a-132">WCF AJAX endpoints always accept both JSON and XML requests.</span></span>  
  
 <span data-ttu-id="be73a-133">HTTP-POST-Anforderungen mit einem Inhaltstyp "Application/JSON" werden als JSON behandelt, und mit dem Inhaltstyp, die XML (z. B. "Text/Xml") angeben, werden als XML behandelt.</span><span class="sxs-lookup"><span data-stu-id="be73a-133">HTTP POST requests with a content-type of "application/json" are treated as JSON, and those with content-type that indicate XML (for example, "text/xml") are treated as XML.</span></span>  
  
 <span data-ttu-id="be73a-134">HTTP GET-Anforderungen enthalten alle Anforderungsparameter in der URL selbst.</span><span class="sxs-lookup"><span data-stu-id="be73a-134">HTTP GET requests contain all the request parameters in the URL itself.</span></span>  
  
 <span data-ttu-id="be73a-135">Es obliegt dem Benutzer zu entscheiden, wie die HTTP-Anforderung für den Endpunkt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="be73a-135">It is up to the user to decide how to create the HTTP request to the endpoint.</span></span> <span data-ttu-id="be73a-136">Der Benutzer kann umfassend steuern, wie das den Text der Anforderung bildende JSON erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="be73a-136">Also, the user has full control over constructing the JSON that forms the body of the request.</span></span> <span data-ttu-id="be73a-137">Ein Beispiel für eine Anforderung aus JavaScript zu erstellen, finden Sie unter den [AJAX-Dienst mit JSON und XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="be73a-137">For an example of creating a request from JavaScript, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>
