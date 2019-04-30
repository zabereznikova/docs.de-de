---
title: JSONP
ms.date: 03/30/2017
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
ms.openlocfilehash: 37da57a000376f972cd6da9e04be46ddec1b7144
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989884"
---
# <a name="jsonp"></a><span data-ttu-id="82156-102">JSONP</span><span class="sxs-lookup"><span data-stu-id="82156-102">JSONP</span></span>
<span data-ttu-id="82156-103">In diesem Beispiel wird erläutert, wie JSON mit Padding (JSONP) in WCF REST-Diensten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="82156-103">This sample demonstrates how to support JSON with Padding (JSONP) in WCF REST services.</span></span> <span data-ttu-id="82156-104">JSONP ist eine Konvention, die zum Aufrufen domänenübergreifender Skripts durch das Generieren von Skripttags im aktuellen Dokument verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="82156-104">JSONP is a convention used to invoke cross-domain scripts by generating script tags in the current document.</span></span> <span data-ttu-id="82156-105">Das Ergebnis wird in einer festgelegten Rückruffunktion zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="82156-105">The result is returned in a specified callback function.</span></span> <span data-ttu-id="82156-106">JSONP basiert auf der Idee, die tags wie `<script src="http://..." >` Skripts aus einer beliebigen Domäne auswerten können und das durch diese Tags abgerufene Skript innerhalb eines Bereichs, in dem andere Funktionen möglicherweise bereits definiert, ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="82156-106">JSONP is based on the idea that tags such as `<script src="http://..." >` can evaluate scripts from any domain and the script retrieved by those tags is evaluated within a scope in which other functions may already be defined.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="82156-107">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="82156-107">Demonstrates</span></span>
 <span data-ttu-id="82156-108">Domänenübergreifende Skripterstellung mit JSONP</span><span class="sxs-lookup"><span data-stu-id="82156-108">Cross-domain scripting with JSONP.</span></span>

## <a name="discussion"></a><span data-ttu-id="82156-109">Diskussion</span><span class="sxs-lookup"><span data-stu-id="82156-109">Discussion</span></span>
 <span data-ttu-id="82156-110">Das Beispiel enthält eine Webseite, für die dynamisch ein Skriptblock hinzugefügt wird, nachdem die Seite im Browser gerendert wurde.</span><span class="sxs-lookup"><span data-stu-id="82156-110">The sample includes a Web page that dynamically adds a script block after the page has been rendered in the browser.</span></span> <span data-ttu-id="82156-111">Dieser Skriptblock ruft einen WCF REST-Dienst auf, der nur über den einen Vorgang `GetCustomer` verfügt.</span><span class="sxs-lookup"><span data-stu-id="82156-111">This script block calls a WCF REST service that has a single operation, `GetCustomer`.</span></span> <span data-ttu-id="82156-112">Der WCF REST-Dienst gibt den Namen und die Adresse eines Kunden durch Wrapping in einen Rückruffunktionsnamen zurück.</span><span class="sxs-lookup"><span data-stu-id="82156-112">The WCF REST service returns a customer’s name and address wrapped in a callback function name.</span></span> <span data-ttu-id="82156-113">Wenn der WCF REST-Dienst antwortet, wird die Rückruffunktion auf der Webseite mithilfe der Kundendaten aufgerufen, und die Rückruffunktion zeigt die Daten auf der Webseite an.</span><span class="sxs-lookup"><span data-stu-id="82156-113">When the WCF REST service responds, the callback function on the Web page is invoked with the customer data and the callback function displays the data on the Web page.</span></span> <span data-ttu-id="82156-114">Die Einfügung des Skripttags und die Ausführung der Rückruffunktion werden automatisch vom ASP.NET AJAX ScriptManager-Steuerelement behandelt.</span><span class="sxs-lookup"><span data-stu-id="82156-114">The injection of the script tag and the execution of the callback function is automatically handled by the ASP.NET AJAX ScriptManager control.</span></span> <span data-ttu-id="82156-115">Das Verwendungsmuster stimmt mit dem aller ASP.NET AJAX-Proxys überein, allerdings mit einer zusätzlichen Zeile zur Aktivierung von JSONP. Dies wird im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="82156-115">The usage pattern is the same as with all ASP.NET AJAX proxies, with the addition of one line to enable JSONP, as shown in the following code:</span></span>

```csharp
var proxy = new JsonpAjaxService.CustomerService();
proxy.set_enableJsonp(true);
proxy.GetCustomer(onSuccess, onFail, null);
```

 <span data-ttu-id="82156-116">Die Webseite kann den WCF REST-Dienst aufrufen, da der Dienst den <xref:System.ServiceModel.Description.WebScriptEndpoint> verwendet, wobei `crossDomainScriptAccessEnabled` auf `true` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="82156-116">The Web page can call the WCF REST service because the service is using the <xref:System.ServiceModel.Description.WebScriptEndpoint> with `crossDomainScriptAccessEnabled` set to `true`.</span></span> <span data-ttu-id="82156-117">Beide Konfigurationen erfolgen in der Datei "Web.config" unter der \<system.serviceModel > Element.</span><span class="sxs-lookup"><span data-stu-id="82156-117">Both of these configurations are done in the Web.config file under the \<system.serviceModel> element.</span></span>

```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

 <span data-ttu-id="82156-118">ScriptManager verwaltet die Interaktion mit dem Dienst und macht damit die Komplexität, die mit einer manuellen Implementierung des JSONP-Zugriffs verbunden ist, überflüssig.</span><span class="sxs-lookup"><span data-stu-id="82156-118">ScriptManager manages the interaction with the service and hides away the complexity of manually implementing JSONP access.</span></span> <span data-ttu-id="82156-119">Wenn `crossDomainScriptAccessEnabled` nastaven NA hodnotu `true` und das Format der Antwort für einen Vorgang ist JSON ist, wird die WCF-Infrastruktur uberprüft die Anforderung für eine rückrufabfrage und dient als Wrapper für die JSON-Antwort mit dem Wert der Abfragezeichenfolge Rückruf der Parameter.</span><span class="sxs-lookup"><span data-stu-id="82156-119">When `crossDomainScriptAccessEnabled` is set to `true` and the response format for an operation is JSON, the WCF infrastructure inspects the URI of the request for a callback query string parameter and wraps the JSON response with the value of the callback query string parameter.</span></span> <span data-ttu-id="82156-120">Im Beispiel ruft die Webseite den WCF REST-Dienst mit dem folgenden URI auf.</span><span class="sxs-lookup"><span data-stu-id="82156-120">In the sample, the Web page calls the WCF REST service with the following URI.</span></span>

```
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0
```

 <span data-ttu-id="82156-121">Da der Zeichenfolgenparameter der Rückrufabfrage über den Wert `JsonPCallback` verfügt, gibt der WCF-Dienst die im folgenden Beispiel dargestellte JSONP-Antwort zurück.</span><span class="sxs-lookup"><span data-stu-id="82156-121">Because the callback query string parameter has a value of `JsonPCallback`, the WCF service returns a JSONP response shown in the following example.</span></span>

```
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});
```

 <span data-ttu-id="82156-122">Diese JSONP-Antwort enthält die als JSON formatierten Kundendaten, für die mit dem von der Webseite angeforderten Rückruffunktionsnamen ein Wrapping ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="82156-122">This JSONP response includes the customer data formatted as JSON, wrapped with the callback function name that the Web page requested.</span></span> <span data-ttu-id="82156-123">ScriptManager führt diesen Rückruf mithilfe eines Skripttags aus, um die domänenübergreifende Anforderung zu ermöglichen und danach das Ergebnis an den onSuccess-Handler zu übergeben, der an die GetCustomer-Operation des ASP.NET AJAX-Proxys übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="82156-123">ScriptManager will execute this callback using a script tag to accomplish the cross-domain request, and then pass the result to the onSuccess handler that was passed to the GetCustomer operation of the ASP.NET AJAX proxy.</span></span>

 <span data-ttu-id="82156-124">Das Beispiel besteht aus zwei ASP.NET-Webanwendungen: eine enthält nur einen WCF-Dienst, und eine andere ASPX-Webseite, die den Dienst aufruft.</span><span class="sxs-lookup"><span data-stu-id="82156-124">The sample consists of two ASP.NET web applications: one contains just a WCF service, and another one contains the .aspx webpage, which calls the service.</span></span> <span data-ttu-id="82156-125">Wenn Sie die Projektmappe ausführen zu können, hostet Visual Studio 2012 die beiden Websites über unterschiedliche Ports und entsteht eine Umgebung, in dem Dienst und Client in verschiedenen Domänen Leben.</span><span class="sxs-lookup"><span data-stu-id="82156-125">When running the solution, Visual Studio 2012 will host the two websites on different ports, which creates an environment where the service and client live on different domains.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="82156-126">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="82156-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="82156-127">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="82156-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="82156-128">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="82156-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82156-129">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="82156-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="82156-130">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="82156-130">To run the sample</span></span>  
  
1. <span data-ttu-id="82156-131">Öffnen Sie die Projektmappe für das JSONP-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="82156-131">Open the solution for the JSONP Sample.</span></span>  
  
2. <span data-ttu-id="82156-132">Drücken Sie F5 zum Starten `http://localhost:26648/JSONPClientPage.aspx` im Browser.</span><span class="sxs-lookup"><span data-stu-id="82156-132">Press F5 to launch `http://localhost:26648/JSONPClientPage.aspx` in the browser.</span></span>  
  
3. <span data-ttu-id="82156-133">Beachten Sie, dass nach dem Laden der Seite die Texteingaben für "Name" und "Address" mit Werten aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="82156-133">Notice that after the page loads, the text inputs for "Name" and "Address" are populated by values.</span></span>  <span data-ttu-id="82156-134">Diese Werte wurden von einem Aufruf an den WCF-Dienst bereitgestellt, nach dem der Browser Rendern der Seite.</span><span class="sxs-lookup"><span data-stu-id="82156-134">These values were supplied from a call to the WCF service after the browser finished rendering the page.</span></span>
