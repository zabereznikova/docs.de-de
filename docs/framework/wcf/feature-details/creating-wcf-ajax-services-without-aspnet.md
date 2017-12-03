---
title: Erstellen von WCF AJAX-Diensten ohne ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4ff3e41608c9b879bd64e004fcae5e87599e0b4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a><span data-ttu-id="5a66e-102">Erstellen von WCF AJAX-Diensten ohne ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5a66e-102">Creating WCF AJAX Services without ASP.NET</span></span>
<span data-ttu-id="5a66e-103">Auf [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] AJAX-Dienste kann von jeder JavaScript-aktivierten Webseite zugegriffen werden, ohne dass ASP.NET AJAX erforderlich wäre.</span><span class="sxs-lookup"><span data-stu-id="5a66e-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] AJAX services can be accessed from any JavaScript-enabled Web page, without requiring ASP.NET AJAX.</span></span> <span data-ttu-id="5a66e-104">In diesem Thema wird beschrieben, wie ein solcher [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5a66e-104">This topic describes how to create such a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="5a66e-105">Anweisungen zur Verwendung [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit ASP.NET AJAX finden Sie unter [Erstellen von WCF-Diensten für ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).</span><span class="sxs-lookup"><span data-stu-id="5a66e-105">For instructions on using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see [Creating WCF Services for ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).</span></span>  
  
 <span data-ttu-id="5a66e-106">Zur Erstellung eines funktionsfähigen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX-Diensts sind drei Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="5a66e-106">There are three parts to a creating a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX service:</span></span>  
  
-   <span data-ttu-id="5a66e-107">Erstellen eines AJAX-Endpunkts, auf den vom Browser aus zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5a66e-107">Creating an AJAX endpoint that can be accessed from the browser.</span></span>  
  
-   <span data-ttu-id="5a66e-108">Erstellen eines AJAX-kompatiblen Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="5a66e-108">Creating an AJAX-compatible service contract.</span></span>  
  
-   <span data-ttu-id="5a66e-109">Zugreifen auf den WCF AJAX-Dienst.</span><span class="sxs-lookup"><span data-stu-id="5a66e-109">Accessing WCF AJAX services.</span></span>  
  
## <a name="creating-an-ajax-endpoint"></a><span data-ttu-id="5a66e-110">Erstellen eines AJAX-Endpunkts</span><span class="sxs-lookup"><span data-stu-id="5a66e-110">Creating an AJAX Endpoint</span></span>  
 <span data-ttu-id="5a66e-111">Der einfachste Weg, AJAX-Unterstützunmg in einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst zu aktivieren, besteht darin, in der dem Dienst zugeordneten SVC-Datei die <xref:System.ServiceModel.Activation.WebServiceHostFactory> zu verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a66e-111">The most basic way to enable AJAX support in a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is to use the <xref:System.ServiceModel.Activation.WebServiceHostFactory> in the .svc file associated with the service, as in the following example.</span></span>  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 <span data-ttu-id="5a66e-112">Alternativ können Sie auch die Konfiguration verwenden, um einen AJAX-Endpunkt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5a66e-112">Alternatively, you can also use configuration to add an AJAX endpoint.</span></span> <span data-ttu-id="5a66e-113">Verwenden Sie die <xref:System.ServiceModel.WebHttpBinding> des Dienstendpunkts, und konfigurieren Sie diesen Endpunkt mit dem <xref:System.ServiceModel.Description.WebHttpBehavior>, wie im folgenden Codeausschnitt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5a66e-113">Use the <xref:System.ServiceModel.WebHttpBinding> on the service endpoint and configure that endpoint with the <xref:System.ServiceModel.Description.WebHttpBehavior> as shown in the following code snippet.</span></span>  
  
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
  
 <span data-ttu-id="5a66e-114">Ein Arbeitsbeispiel finden Sie unter der [AJAX-Dienst mit JSON und XML-](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5a66e-114">For a working example, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="creating-an-ajax-compatible-service-contract"></a><span data-ttu-id="5a66e-115">Erstellen eines AJAX-kompatiblen Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="5a66e-115">Creating an AJAX-Compatible Service Contract</span></span>  
 <span data-ttu-id="5a66e-116">Standardmäßig geben die über einem AJAX-Endpunkt verfügbar gemachten Dienstverträge Daten im XML-Format zurück.</span><span class="sxs-lookup"><span data-stu-id="5a66e-116">By default, service contracts exposed over an AJAX endpoint return data in the XML format.</span></span> <span data-ttu-id="5a66e-117">Ebenso standardmäßig kann auf die Dienstvorgänge über HTTP POST-Anforderungen mit URLs zugegriffen werden, die die Endpunktadresse gefolgt vom Vorgangsnamen enthalten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a66e-117">Also, by default service operations are accessible through HTTP POST requests to URLs that include the endpoint address followed by the operation name, as shown in the following example.</span></span>  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 <span data-ttu-id="5a66e-118">Dieser Vorgang ist mit HTTP POST für `http://serviceaddress/endpointaddress/GetCities` und zurückgeben eine XML-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="5a66e-118">This operation is accessible using an HTTP POST to `http://serviceaddress/endpointaddress/GetCities` and return an XML message.</span></span>  
  
 <span data-ttu-id="5a66e-119">Sie können das vollständige Webprogrammiermodell verwenden, um diese grundlegenden Aspekte anzupassen.</span><span class="sxs-lookup"><span data-stu-id="5a66e-119">You can use the full Web Programming Model to customize these basic aspects.</span></span> <span data-ttu-id="5a66e-120">Sie können beispielsweise die Attribute <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> verwenden, um zu steuern, auf welche HTTP-Verben der Vorgang reagiert, oder die Eigenschaft `UriTemplate` dieser jeweiligen Attribute verwenden, um benutzerdefinierte URIs anzugeben usw.</span><span class="sxs-lookup"><span data-stu-id="5a66e-120">For example, you can use the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to control the HTTP verb to which the operation responds or use the `UriTemplate` property of these respective attributes to specify custom URIs.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="5a66e-121">die [WCF Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="5a66e-121"> the [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) topic.</span></span>  
  
 <span data-ttu-id="5a66e-122">Das JSON-Datenformat wird oft in AJAX-Diensten verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a66e-122">The JSON data format is often used in AJAX services.</span></span> <span data-ttu-id="5a66e-123">Um einen Vorgang zu erstellen, der JSON statt XML zurückgibt, legen Sie die <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A>-Eigenschaft (oder die <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>-Eigenschaft) auf <xref:System.ServiceModel.Web.WebMessageFormat.Json> fest.</span><span class="sxs-lookup"><span data-stu-id="5a66e-123">To create an operation that returns JSON instead of XML, set the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (or the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) property to <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="5a66e-124">Die [eigenständige JSON-Serialisierung](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) Thema zeigt wie integrierte .NET Typen und Daten Vertrag Typen Zuordnung zu JSON.</span><span class="sxs-lookup"><span data-stu-id="5a66e-124">The [Stand-Alone JSON Serialization](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) topic shows how built-in .NET types and data contract types map to JSON.</span></span>  
  
 <span data-ttu-id="5a66e-125">Normalerweise bestehen JSON-Anforderungen und -Antworten aus nur einem Element.</span><span class="sxs-lookup"><span data-stu-id="5a66e-125">Normally, JSON requests and responses consist of just one item.</span></span> <span data-ttu-id="5a66e-126">Für den vorangehenden `GetCities`-Vorgang ähnelt die Anforderung der folgenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5a66e-126">For the preceding `GetCities` operation, the request resembles the following statement.</span></span>  
  
```  
"na"  
```  
  
 <span data-ttu-id="5a66e-127">Die Antwort auf diese Anforderung ähnelt der folgenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5a66e-127">The response to that request resembles the following statement.</span></span>  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 <span data-ttu-id="5a66e-128">Wenn der Vorgang einen zusätzlichen Parameter annimmt, muss der Anforderungsstil auf "wrapped" festgelegt werden, damit beide Parameter einem einzigen JSON-Objekt zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="5a66e-128">If the operation takes an extra parameter, the request style must be wrapped to wrap both parameters in a single JSON object.</span></span> <span data-ttu-id="5a66e-129">Ein Beispiel für eine JSON-Nachricht in diesem Stil finden Sie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5a66e-129">An example of this style JSON message is in the following example.</span></span>  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 <span data-ttu-id="5a66e-130">Der folgende Vertrag akzeptiert diese Nachricht.</span><span class="sxs-lookup"><span data-stu-id="5a66e-130">The following contract accepts this message.</span></span>  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a><span data-ttu-id="5a66e-131">Zugreifen auf AJAX-Dienste</span><span class="sxs-lookup"><span data-stu-id="5a66e-131">Accessing AJAX Services</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5a66e-132">AJAX-Endpunkte akzeptieren immer sowohl JSON- als auch XML-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="5a66e-132"> AJAX endpoints always accept both JSON and XML requests.</span></span>  
  
 <span data-ttu-id="5a66e-133">HTTP POST-Anforderungen mit einem Inhaltstyp "Application/Json" werden als JSON behandelt, und mit dem Inhaltstyp, die XML (z. B. "Text/Xml") angeben, werden als XML behandelt.</span><span class="sxs-lookup"><span data-stu-id="5a66e-133">HTTP POST requests with a content-type of "application/json" are treated as JSON, and those with content-type that indicate XML (for example, "text/xml") are treated as XML.</span></span>  
  
 <span data-ttu-id="5a66e-134">HTTP GET-Anforderungen enthalten alle Anforderungsparameter in der URL selbst.</span><span class="sxs-lookup"><span data-stu-id="5a66e-134">HTTP GET requests contain all the request parameters in the URL itself.</span></span>  
  
 <span data-ttu-id="5a66e-135">Es obliegt dem Benutzer zu entscheiden, wie die HTTP-Anforderung für den Endpunkt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5a66e-135">It is up to the user to decide how to create the HTTP request to the endpoint.</span></span> <span data-ttu-id="5a66e-136">Der Benutzer kann umfassend steuern, wie das den Text der Anforderung bildende JSON erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5a66e-136">Also, the user has full control over constructing the JSON that forms the body of the request.</span></span> <span data-ttu-id="5a66e-137">Ein Beispiel für eine Anforderung aus JavaScript zu erstellen, finden Sie unter der [AJAX-Dienst mit JSON und XML-](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5a66e-137">For an example of creating a request from JavaScript, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>
