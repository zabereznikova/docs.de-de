---
title: AJAX-Dienst mit HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: f904a26d87a21a931035b45261dbcd970f7d63a1
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="ajax-service-using-http-post"></a>AJAX-Dienst mit HTTP POST
Dieses Beispiel veranschaulicht, wie Windows Communication Foundation (WCF) zum Erstellen einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX)-Dienst, der HTTP POST verwendet. Bei einem AJAX-Dienst handelt es sich um einen Dienst, auf den Sie mit einfachem JavaScript-Code von einem Webbrowserclient aus zugreifen können. Dieses Beispiel baut auf den [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ; der einzige Unterschied zwischen den zwei Beispielen wird die Verwendung von HTTP POST anstelle von HTTP GET-Sample.  
  
 AJAX-Unterstützung in Windows Communication Foundation (WCF) ist optimiert für die Verwendung mit ASP.NET AJAX über das `ScriptManager` Steuerelement. Ein Beispiel der Verwendung von WCF mit ASP.NET AJAX finden Sie unter der [Ajax-Beispielen](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Der Dienst im folgenden Beispiel ist ein WCF-Dienst ohne AJAX-spezifischen Code.  
  
 Wenn die <xref:System.ServiceModel.Web.WebInvokeAttribute> -Attribut angewendet wird, in einem Vorgang oder die <xref:System.ServiceModel.Web.WebGetAttribute> -Attribut nicht angewendet wird, wird das standardmäßige HTTP-Verb ("POST") verwendet. POST-Anforderungen sind schwieriger zu erstellen als GET-Anforderungen, sie werden jedoch nicht zwischengespeichert. Verwenden Sie POST-Anforderungen für alle Vorgänge, bei denen keine Zwischenspeicherung benötigt wird.  

```csharp
[ServiceContract(Namespace = "PostAjaxService")]  
public interface ICalculator  
{
    [WebInvoke]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}
```

 Erstellen Sie im Dienst mithilfe von <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> einen AJAX-Endpunkt wie im Beispiel "Einfacher AJAX-Dienst".  
  
 Im Gegensatz zu GET-Anforderungen können Sie POST-Dienste nicht aus dem Browser aufrufen. Beispielsweise zum Navigieren http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 führt zu einem Fehler, da der POST-Dienst erwartet, dass die `n1` und `n2` Parameter im Text Nachricht gesendet werden – im JSON-Format – und nicht in der URL.  
  
 Die Clientwebseite "PostAjaxClientPage.aspx" enthält ASP.NET-Code zum Aufrufen des Diensts, wenn der Benutzer auf eine der Vorgangsschaltflächen auf der Seite klickt. Der Dienst reagiert auf die gleiche Weise wie in der [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel mit dem GET-Anforderung.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie die setupanweisungen ausführen [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Erstellen Sie die Projektmappe PostAjaxService.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Navigieren Sie zu http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (Öffnen Sie "postajaxclientpage.aspx" nicht aus dem Projektverzeichnis im Browser).  
  
## <a name="see-also"></a>Siehe auch
