---
title: Beispiel für AJAX-Dienst mit JSON und XML
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: ca9bdbfa135ac7dc0b69589d4f8fce07bc4c4afe
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716217"
---
# <a name="ajax-service-with-json-and-xml-sample"></a><span data-ttu-id="f1e29-102">Beispiel für AJAX-Dienst mit JSON und XML</span><span class="sxs-lookup"><span data-stu-id="f1e29-102">AJAX Service with JSON and XML Sample</span></span>

<span data-ttu-id="f1e29-103">In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) verwendet wird, um einen asynchronen JavaScript-und XML (Ajax)-Dienst zu erstellen, der entweder JavaScript Object Notation (JSON)-oder XML-Daten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f1e29-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an Asynchronous JavaScript and XML (AJAX) service that returns either JavaScript Object Notation (JSON) or XML data.</span></span> <span data-ttu-id="f1e29-104">Sie können auf einen AJAX-Dienst zugreifen, indem Sie JavaScript-Code in einem Webbrowserclient verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1e29-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="f1e29-105">Dieses Beispiel baut auf dem [grundlegenden AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel auf.</span><span class="sxs-lookup"><span data-stu-id="f1e29-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>

<span data-ttu-id="f1e29-106">Im Gegensatz zu den anderen AJAX-Beispielen werden in diesem Beispiel ASP.NET AJAX und das <xref:System.Web.UI.ScriptManager>-Steuerelement nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f1e29-106">Unlike the other AJAX samples, this sample does not use ASP.NET AJAX and the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="f1e29-107">Mit einigen zusätzlichen Konfigurationen kann von jeder HTML-Seite über JavaScript auf WCF AJAX-Dienste zugegriffen werden. dieses Szenario wird hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1e29-107">With some additional configuration, WCF AJAX services can be accessed from any HTML page through JavaScript, and this scenario is shown here.</span></span> <span data-ttu-id="f1e29-108">Ein Beispiel für die Verwendung von WCF mit ASP.NET AJAX finden Sie unter [AJAX Samples](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="f1e29-108">For an example of using WCF with ASP.NET AJAX, see [AJAX Samples](ajax.md).</span></span>

<span data-ttu-id="f1e29-109">In diesem Beispiel wird gezeigt, wie der Antworttyp eines Vorgangs zwischen JSON und XML umgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="f1e29-109">This sample shows how to switch the response type of an operation between JSON and XML.</span></span> <span data-ttu-id="f1e29-110">Diese Funktion ist unabhängig davon verfügbar, ob der Dienst für den Zugriff durch ASP.NET AJAX oder eine HTML/JavaScript-Clientseite konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="f1e29-110">This functionality is available regardless of whether the service is configured to be accessed by ASP.NET AJAX or by an HTML/JavaScript client page.</span></span>

> [!NOTE]
> <span data-ttu-id="f1e29-111">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="f1e29-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="f1e29-112">Um die Verwendung von Nicht-ASP.NET AJAX-Clients zu aktivieren, verwenden Sie <xref:System.ServiceModel.Activation.WebServiceHostFactory> (nicht <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) in der SVC-Datei.</span><span class="sxs-lookup"><span data-stu-id="f1e29-112">To enable the use of non-ASP.NET AJAX clients, use <xref:System.ServiceModel.Activation.WebServiceHostFactory> (not <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) in the .svc file.</span></span> <span data-ttu-id="f1e29-113"><xref:System.ServiceModel.Activation.WebServiceHostFactory> fügt dem Dienst einen <xref:System.ServiceModel.Description.WebHttpEndpoint>-Standardendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="f1e29-113"><xref:System.ServiceModel.Activation.WebServiceHostFactory> adds a <xref:System.ServiceModel.Description.WebHttpEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="f1e29-114">Der Endpunkt wird mit einer leeren Adresse relativ zur SVC-Datei konfiguriert. Dies bedeutet, dass die Adresse des Dienstanbieter `http://localhost/ServiceModelSamples/service.svc`ist, ohne dass zusätzliche Suffixe den Vorgangs Namen haben.</span><span class="sxs-lookup"><span data-stu-id="f1e29-114">The endpoint is configured at an empty address relative to the .svc file; this means that the address of the service is `http://localhost/ServiceModelSamples/service.svc`, with no additional suffixes other than the operation name.</span></span>

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>`

<span data-ttu-id="f1e29-115">Im folgenden Abschnitt in der Datei Web.config können zusätzliche Konfigurationsänderungen am Endpunkt vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="f1e29-115">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="f1e29-116">Wenn keine zusätzlichen Änderungen erforderlich sind, kann der Abschnitt entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f1e29-116">It can be removed if no extra changes are needed.</span></span>

```xml
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <!-- Use this element to configure the endpoint -->
      <standardEndpoint name="" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

<span data-ttu-id="f1e29-117">Das Standarddatenformat für <xref:System.ServiceModel.Description.WebHttpEndpoint> ist XML, während das Standarddatenformat für <xref:System.ServiceModel.Description.WebScriptEndpoint> JSON ist.</span><span class="sxs-lookup"><span data-stu-id="f1e29-117">The default data format for <xref:System.ServiceModel.Description.WebHttpEndpoint> is XML, while the default data format for <xref:System.ServiceModel.Description.WebScriptEndpoint> is JSON.</span></span> <span data-ttu-id="f1e29-118">Weitere Informationen finden Sie unter [Erstellen von WCF AJAX-Diensten ohne ASP.net](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="f1e29-118">For more information, see [Creating WCF AJAX Services without ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).</span></span>

<span data-ttu-id="f1e29-119">Der Dienst im folgenden Beispiel ist ein WCF-Standard Dienst mit zwei Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="f1e29-119">The service in the following sample is a standard WCF service with two operations.</span></span> <span data-ttu-id="f1e29-120">Beide Vorgänge erfordern den <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped>-Textstil beim <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut oder <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attribut. Dieser Textstil ist typisch für das `webHttp`-Verhalten und hat keinen Einfluss auf den JSON/XML-Datenformatwechsel.</span><span class="sxs-lookup"><span data-stu-id="f1e29-120">Both operations require the <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> body style on the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes, which is specific to the `webHttp` behavior and has no bearing on the JSON/XML data format switch.</span></span>

```csharp
[OperationContract]
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]
MathResult DoMathXml(double n1, double n2);
```

<span data-ttu-id="f1e29-121">Das Antwortformat für den Vorgang wird als XML angegeben. Dies ist die Standardeinstellung für das [\<webHttp->](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) Verhalten.</span><span class="sxs-lookup"><span data-stu-id="f1e29-121">The response format for the operation is specified as XML, which is the default setting for the [\<webHttp>](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="f1e29-122">Es wird jedoch empfohlen, das Antwortformat explizit festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f1e29-122">However, it is good practice explicitly specify the response format.</span></span>

<span data-ttu-id="f1e29-123">Der andere Vorgang verwendet das `WebInvokeAttribute`-Attribut und gibt explizit JSON statt XML als Antwortformat an.</span><span class="sxs-lookup"><span data-stu-id="f1e29-123">The other operation uses the `WebInvokeAttribute` attribute and explicitly specifies JSON instead of XML for the response.</span></span>

```csharp
[OperationContract]
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]
MathResult DoMathJson(double n1, double n2);
```

<span data-ttu-id="f1e29-124">Beachten Sie, dass die Vorgänge in beiden Fällen einen komplexen Typ zurückgeben, `MathResult`, bei dem es sich um einen WCF-Standarddaten Vertragstyp handelt.</span><span class="sxs-lookup"><span data-stu-id="f1e29-124">Note that in both cases the operations return a complex type, `MathResult`, which is a standard WCF data contract type.</span></span>

<span data-ttu-id="f1e29-125">Die Client Webseite XmlAjaxClientPage. htm enthält JavaScript-Code, der einen der vorherigen beiden Vorgänge aufruft, wenn der Benutzer auf die Schaltflächen **Berechnung ausführen (JSON zurückgeben)** oder **Berechnung (Rückgabe-XML)** auf der Seite klickt.</span><span class="sxs-lookup"><span data-stu-id="f1e29-125">The client Web page XmlAjaxClientPage.htm contains JavaScript code that invokes one of the preceding two operations when the user clicks the **Perform calculation (return JSON)** or **Perform calculation (return XML)** buttons on the page.</span></span> <span data-ttu-id="f1e29-126">Im zum Aufrufen des Diensts verwendeten Code wird ein JSON-Text erstellt und mit HTTP-POST gesendet.</span><span class="sxs-lookup"><span data-stu-id="f1e29-126">The code to invoke the service constructs a JSON body and sends it using HTTP POST.</span></span> <span data-ttu-id="f1e29-127">Die Anforderung wird manuell in JavaScript erstellt, im Gegensatz zum [grundlegenden AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel und den anderen Beispielen mit ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="f1e29-127">The request is created manually in JavaScript, unlike the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample and the other samples using ASP.NET AJAX.</span></span>

```csharp
// Create HTTP request
var xmlHttp;
// Request instantiation code omitted…
// Result handler code omitted…

// Build the operation URL
var url = "service.svc/ajaxEndpoint/";
url = url + operation;

// Build the body of the JSON message
var body = '{"n1":';
body = body + document.getElementById("num1").value + ',"n2":';
body = body + document.getElementById("num2").value + '}';

// Send the HTTP request
xmlHttp.open("POST", url, true);
xmlHttp.setRequestHeader("Content-type", "application/json");
xmlHttp.send(body);
```

<span data-ttu-id="f1e29-128">Wenn der Dienst antwortet, wird die Antwort, ohne vorher weiterverarbeitet zu werden, in einem Textfeld auf der Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1e29-128">When the service responds, the response is displayed without any further processing in a textbox on the page.</span></span> <span data-ttu-id="f1e29-129">Dies dient der Veranschaulichung, sodass Sie direkt die verwendeten XML- und JSON-Datenformate prüfen können.</span><span class="sxs-lookup"><span data-stu-id="f1e29-129">This is implemented for demonstration purposes to allow you to directly observe the XML and JSON data formats used.</span></span>

```javascript
// Create result handler
xmlHttp.onreadystatechange=function(){
     if(xmlHttp.readyState == 4){
          document.getElementById("result").value = xmlHttp.responseText;
     }
}
```

> [!IMPORTANT]
> <span data-ttu-id="f1e29-130">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f1e29-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f1e29-131">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f1e29-131">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f1e29-132">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="f1e29-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f1e29-133">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f1e29-133">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f1e29-134">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="f1e29-134">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="f1e29-135">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="f1e29-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="f1e29-136">Erstellen Sie die Projekt Mappe XmlAjaxService. sln, wie unter [Erstellen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f1e29-136">Build the solution XmlAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="f1e29-137">Navigieren Sie zu `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (Öffnen Sie XmlAjaxClientPage. htm nicht im Browser im Projektverzeichnis).</span><span class="sxs-lookup"><span data-stu-id="f1e29-137">Navigate to `http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm` (do not open XmlAjaxClientPage.htm in the browser from the project directory).</span></span>

## <a name="see-also"></a><span data-ttu-id="f1e29-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1e29-138">See also</span></span>

- [<span data-ttu-id="f1e29-139">AJAX-Dienst mit HTTP POST</span><span class="sxs-lookup"><span data-stu-id="f1e29-139">AJAX Service Using HTTP POST</span></span>](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
