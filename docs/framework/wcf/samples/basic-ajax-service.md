---
title: Einfacher AJAX-Dienst
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: d8da6469101511b6b5a9ce19a11f1e5e3fe9d83e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524882"
---
# <a name="basic-ajax-service"></a><span data-ttu-id="680be-102">Einfacher AJAX-Dienst</span><span class="sxs-lookup"><span data-stu-id="680be-102">Basic AJAX Service</span></span>
<span data-ttu-id="680be-103">In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) zu verwenden, um das Erstellen eines einfachen (ASP.NET Asynchronous JavaScript and XML (AJAX)-Diensts (ein Dienst, die Sie mithilfe von JavaScript-Codes über einen Webbrowserclient zugreifen können).</span><span class="sxs-lookup"><span data-stu-id="680be-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access using JavaScript code from a Web browser client).</span></span> <span data-ttu-id="680be-104">Der Dienst nutzt das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut, um sicherzustellen, dass der Dienst auf HTTP GET-Anforderungen antwortet und für die Verwendung von JSON-Daten (JavaScript Object Notation) für Antworten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="680be-104">The service uses the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to ensure that the service responds to HTTP GET requests and is configured to use the JavaScript Object Notation (JSON) data format for responses.</span></span>  
  
 <span data-ttu-id="680be-105">AJAX-Unterstützung in WCF ist optimiert für die Verwendung mit ASP.NET AJAX über das `ScriptManager` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="680be-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="680be-106">Ein Beispiel der Verwendung von WCF mit ASP.NET AJAX finden Sie unter den [AJAX-Beispielen](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="680be-106">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="680be-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="680be-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="680be-108">Im folgenden Code wird das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut auf den `Add`-Vorgang angewandt, um sicherzustellen, dass der Dienst auf HTTP GET-Anforderungen antwortet.</span><span class="sxs-lookup"><span data-stu-id="680be-108">In the following code, the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is applied to the `Add` operation to ensure that the service responds to HTTP GET requests.</span></span> <span data-ttu-id="680be-109">Der Einfachheit halber nutzt der Code GET (Sie können eine HTTP GET-Anforderung von jedem Webbrowser aus erstellen).</span><span class="sxs-lookup"><span data-stu-id="680be-109">The code uses GET for simplicity (you can construct an HTTP GET request from any Web browser).</span></span> <span data-ttu-id="680be-110">Sie können GET auch verwenden, um Caching zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="680be-110">You can also use GET to enable caching.</span></span> <span data-ttu-id="680be-111">Bei Fehlen des `WebGetAttribute`-Attributs ist die Standardeinstellung HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="680be-111">HTTP POST is the default in the absence of the `WebGetAttribute` attribute.</span></span>  

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

 <span data-ttu-id="680be-112">Die SVC-Beispieldatei verwendet <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, wodurch dem Dienst ein <xref:System.ServiceModel.Description.WebScriptEndpoint>-Standardendpunkt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="680be-112">The sample .svc file uses <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, which adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="680be-113">Der Endpunkt wird an einer leeren Adresse relativ zur SVC-Datei konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="680be-113">The endpoint is configured at an empty address relative to the .svc file.</span></span> <span data-ttu-id="680be-114">Dies bedeutet, dass die Adresse des Diensts http://localhost/ServiceModelSamples/service.svc, mit Ausnahme des Vorgangsnamens keine zusätzlichen Suffixe.</span><span class="sxs-lookup"><span data-stu-id="680be-114">This means that the address of the service is http://localhost/ServiceModelSamples/service.svc, with no additional suffixes other than the operation name.</span></span>  

```svc
<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>
```

 <span data-ttu-id="680be-115">Der <xref:System.ServiceModel.Description.WebScriptEndpoint> ist so vorkonfiguriert, dass von einer ASP.NET AJAX-Clientseite aus auf den Dienst zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="680be-115">The <xref:System.ServiceModel.Description.WebScriptEndpoint> is pre-configured to make the service accessible from an ASP.NET AJAX client page.</span></span> <span data-ttu-id="680be-116">Im folgenden Abschnitt in der Datei Web.config können zusätzliche Konfigurationsänderungen am Endpunkt vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="680be-116">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="680be-117">Wenn keine zusätzlichen Änderungen erforderlich sind, kann der Abschnitt entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="680be-117">It can be removed if no extra changes are required.</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name=""  />  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="680be-118">Der <xref:System.ServiceModel.Description.WebScriptEndpoint> legt das Standarddatenformat für den Dienst auf JSON anstelle von XML fest.</span><span class="sxs-lookup"><span data-stu-id="680be-118">The <xref:System.ServiceModel.Description.WebScriptEndpoint> sets the default data format for the service to JSON instead of XML.</span></span> <span data-ttu-id="680be-119">Um den Dienst aufzurufen, navigieren Sie zu http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 nach dem Ausführen der Reihe nach oben und Buildanweisungen weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="680be-119">To invoke the service, navigate to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 after completing the set up and build steps shown later in this topic.</span></span> <span data-ttu-id="680be-120">Diese Testfunktion wird durch die Verwendung einer HTTP GET-Anforderung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="680be-120">This testing functionality is enabled by the use of a HTTP GET request.</span></span>  
  
 <span data-ttu-id="680be-121">Die Clientwebseite SimpleAjaxClientPage.aspx enthält ASP.NET-Code zum Aufrufen des Diensts, wenn der Benutzer auf eine der Vorgangsschaltflächen auf der Seite klickt.</span><span class="sxs-lookup"><span data-stu-id="680be-121">The client Web page SimpleAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="680be-122">Das `ScriptManager`-Steuerelement wird verwendet, um dem Dienst durch JavaScript einen Proxy verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="680be-122">The `ScriptManager` control is used to make a proxy to the service accessible through JavaScript.</span></span>  

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```

 <span data-ttu-id="680be-123">Der lokale Proxy wird instanziiert, und Vorgänge werden mit dem folgenden JavaScript-Code aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="680be-123">The local proxy is instantiated and operations are invoked using the following JavaScript code.</span></span>  

```javascript
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```

 <span data-ttu-id="680be-124">Ist der Dienstaufruf erfolgreich, ruft der Code einen `onSuccess`-Handler auf, und das Ergebnis des Vorgangs wird in einem Textfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="680be-124">If the service call succeeds, the code invokes the `onSuccess` handler and the result of the operation is displayed in a text box.</span></span>  

```javascript
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}
```

> [!IMPORTANT]
>  <span data-ttu-id="680be-125">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="680be-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="680be-126">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="680be-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="680be-127">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="680be-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="680be-128">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="680be-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="680be-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="680be-129">See Also</span></span>
