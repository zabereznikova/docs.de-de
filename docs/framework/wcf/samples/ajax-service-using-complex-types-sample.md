---
title: Beispiel für AJAX-Dienst mit komplexen Typen
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: 98d33c250be31ac43eef6d76ade997a30af87090
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923690"
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="efbc2-102">Beispiel für AJAX-Dienst mit komplexen Typen</span><span class="sxs-lookup"><span data-stu-id="efbc2-102">AJAX Service Using Complex Types Sample</span></span>
<span data-ttu-id="efbc2-103">In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) verwendet wird, um einen ASP.NET Asynchronous JavaScript and XML (Ajax)-Dienst zu erstellen, der Instanzen komplexer Typen erstellt und diese zwischen Dienst und Client als JavaScript Object Notation (JSON) sendet.</span><span class="sxs-lookup"><span data-stu-id="efbc2-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="efbc2-104">Sie können auf einen AJAX-Dienst zugreifen, indem Sie JavaScript-Code in einem Webbrowserclient verwenden.</span><span class="sxs-lookup"><span data-stu-id="efbc2-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="efbc2-105">Dieses Beispiel baut auf dem [grundlegenden AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel auf.</span><span class="sxs-lookup"><span data-stu-id="efbc2-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="efbc2-106">Die AJAX-Unterstützung in WCF ist für die Verwendung mit ASP.net <xref:System.Web.UI.ScriptManager> AJAX über das-Steuerelement optimiert.</span><span class="sxs-lookup"><span data-stu-id="efbc2-106">AJAX support in WCF is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="efbc2-107">Ein Beispiel für die Verwendung von WCF mit ASP.NET AJAX finden Sie in den [AJAX-Beispielen](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="efbc2-107">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efbc2-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="efbc2-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="efbc2-109">Der Dienst im folgenden Beispiel ist ein WCF-Dienst ohne AJAX-spezifischen Code.</span><span class="sxs-lookup"><span data-stu-id="efbc2-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span> <span data-ttu-id="efbc2-110">Da kein <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut angewendet wird, wird das standardmäßige HTTP-Verb ("POST") verwendet.</span><span class="sxs-lookup"><span data-stu-id="efbc2-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="efbc2-111">Der Dienst hat einen Vorgang, `DoMath`, der einen komplexen Typ namens `MathResult` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="efbc2-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="efbc2-112">Der komplexe Typ ist ein Standarddatenvertragstyp, der ebenfalls keinen AJAX-spezifischen Code enthält.</span><span class="sxs-lookup"><span data-stu-id="efbc2-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>  

```csharp
[DataContract]  
public class MathResult  
{  
    [DataMember]  
    public double sum;  
    [DataMember]  
    public double difference;  
    [DataMember]  
    public double product;  
    [DataMember]  
    public double quotient;  
}  
```

 <span data-ttu-id="efbc2-113">Erstellen Sie im Dienst mithilfe von <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> einen AJAX-Endpunkt wie im Beispiel "Einfacher AJAX-Dienst".</span><span class="sxs-lookup"><span data-stu-id="efbc2-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="efbc2-114">Die ComplexTypeClientPage. aspx-Client Webseite enthält ASP.net-und JavaScript-Code zum Aufrufen des Diensts, wenn der Benutzer auf der Seite auf die Schaltfläche **Berechnung ausführen** klickt.</span><span class="sxs-lookup"><span data-stu-id="efbc2-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="efbc2-115">Der Code zum Aufrufen des Dienstanbieter erstellt einen JSON-Text und sendet ihn mithilfe von HTTP Post, ähnlich dem [AJAX-Dienst unter Verwendung von HTTP Post](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) Sample.</span><span class="sxs-lookup"><span data-stu-id="efbc2-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
 <span data-ttu-id="efbc2-116">Wenn der Dienstaufruf erfolgreich war, können Sie im resultierenden JaveScript-Objekt auf die einzelnen Datenmember (`sum`, `difference`, `product` und `quotient`) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="efbc2-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="efbc2-117">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="efbc2-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="efbc2-118">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="efbc2-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="efbc2-119">Erstellen Sie die Projekt Mappe ComplexTypeAjaxService. sln, wie unter [Erstellen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="efbc2-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="efbc2-120">Navigieren Sie `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` zu (Öffnen Sie ComplexTypeClientPage. aspx im Browser nicht aus dem Projektverzeichnis).</span><span class="sxs-lookup"><span data-stu-id="efbc2-120">Navigate to `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="efbc2-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="efbc2-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="efbc2-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="efbc2-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="efbc2-123">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="efbc2-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="efbc2-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="efbc2-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="efbc2-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efbc2-125">See also</span></span>

- [<span data-ttu-id="efbc2-126">Einfacher AJAX-Dienst</span><span class="sxs-lookup"><span data-stu-id="efbc2-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
