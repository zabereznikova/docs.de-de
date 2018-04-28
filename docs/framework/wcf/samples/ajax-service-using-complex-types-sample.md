---
title: Beispiel für AJAX-Dienst mit komplexen Typen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b821a252e202f0fef719e1545b38b4423237d0c7
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="904ce-102">Beispiel für AJAX-Dienst mit komplexen Typen</span><span class="sxs-lookup"><span data-stu-id="904ce-102">AJAX Service Using Complex Types Sample</span></span>
<span data-ttu-id="904ce-103">In diesem Beispiel wird veranschaulicht, wie mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ein AJAX-Dienst (ASP.NET Asynchronous JavaScript and XML) erstellt werden kann, der Instanzen komplexer Typen erstellt und diese zwischen Dienst und Client als Daten im Datenformat Javascript Object Notation (JSON) sendet.</span><span class="sxs-lookup"><span data-stu-id="904ce-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="904ce-104">Sie können auf einen AJAX-Dienst zugreifen, indem Sie JavaScript-Code in einem Webbrowserclient verwenden.</span><span class="sxs-lookup"><span data-stu-id="904ce-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="904ce-105">Dieses Beispiel baut auf den [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="904ce-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="904ce-106">Die AJAX-Unterstützung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist für die Verwendung mit ASP.NET AJAX über das <xref:System.Web.UI.ScriptManager>-Steuerelement optimiert.</span><span class="sxs-lookup"><span data-stu-id="904ce-106">AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="904ce-107">Ein Beispiel der Verwendung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit ASP.NET AJAX finden Sie unter der [AJAX-Beispielen](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="904ce-107">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [AJAX Samples](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="904ce-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="904ce-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="904ce-109">Der Dienst im folgenden Beispiel ist ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst ohne AJAX-spezifischen Code.</span><span class="sxs-lookup"><span data-stu-id="904ce-109">The service in the following sample is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with no AJAX-specific code.</span></span> <span data-ttu-id="904ce-110">Da kein <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut angewendet wird, wird das standardmäßige HTTP-Verb ("POST") verwendet.</span><span class="sxs-lookup"><span data-stu-id="904ce-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="904ce-111">Der Dienst hat einen Vorgang, `DoMath`, der einen komplexen Typ namens `MathResult` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="904ce-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="904ce-112">Der komplexe Typ ist ein Standarddatenvertragstyp, der ebenfalls keinen AJAX-spezifischen Code enthält.</span><span class="sxs-lookup"><span data-stu-id="904ce-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>  

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

 <span data-ttu-id="904ce-113">Erstellen Sie im Dienst mithilfe von <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> einen AJAX-Endpunkt wie im Beispiel "Einfacher AJAX-Dienst".</span><span class="sxs-lookup"><span data-stu-id="904ce-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="904ce-114">Der Client clientwebseite ComplexTypeClientPage.aspx enthält ASP.NET-Code und JavaScript-Code zum Aufrufen des Diensts, klickt der Benutzer die **Berechnung durchführen** Schaltfläche auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="904ce-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="904ce-115">Der Code zum Aufrufen des Diensts erstellt einen JSON-Text und sendet diese mithilfe von HTTP POST, ähnlich wie die [AJAX-Dienst mithilfe von HTTP-POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="904ce-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
 <span data-ttu-id="904ce-116">Wenn der Dienstaufruf erfolgreich war, können Sie im resultierenden JaveScript-Objekt auf die einzelnen Datenmember (`sum`, `difference`, `product` und `quotient`) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="904ce-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="904ce-117">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="904ce-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="904ce-118">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="904ce-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="904ce-119">Erstellen Sie die Projektmappe ComplexTypeAjaxService.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="904ce-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="904ce-120">Navigieren Sie zu http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (Öffnen Sie ComplexTypeClientPage.aspx nicht aus dem Projektverzeichnis im Browser).</span><span class="sxs-lookup"><span data-stu-id="904ce-120">Navigate to http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="904ce-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="904ce-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="904ce-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="904ce-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="904ce-123">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="904ce-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="904ce-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="904ce-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="904ce-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="904ce-125">See Also</span></span>  
 [<span data-ttu-id="904ce-126">Einfacher AJAX-Dienst</span><span class="sxs-lookup"><span data-stu-id="904ce-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
