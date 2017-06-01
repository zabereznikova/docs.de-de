---
title: "AJAX-Dienst mit HTTP POST | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# AJAX-Dienst mit HTTP POST
In diesem Beispiel wird die Verwendung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zum Erstellen eines [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML \(AJAX\)\-Diensts veranschaulicht, der HTTP POST verwendet. Bei einem AJAX\-Dienst handelt es sich um einen Dienst, auf den Sie mit einfachem JavaScript\-Code von einem Webbrowserclient aus zugreifen können. Dieses Beispiel baut auf dem Beispiel [Einfacher AJAX\-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) auf. Der einzige Unterschied zwischen den beiden Beispielen besteht in der Verwendung von HTTP POST anstelle von HTTP GET.  
  
 Die AJAX\-Unterstützung in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist für die Verwendung mit ASP.NET AJAX über das `ScriptManager`\-Steuerelement optimiert. Ein Beispiel für das Verwenden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit ASP.NET AJAX finden Sie unter [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Der Dienst im folgenden Beispiel ist ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst ohne AJAX\-spezifischen Code.  
  
 Wenn das <xref:System.ServiceModel.Web.WebInvokeAttribute>\-Attribut in einem Vorgang angewendet wird oder das <xref:System.ServiceModel.Web.WebGetAttribute>\-Attribut nicht angewendet wird, wird das HTTP\-Standardverb \("POST"\) verwendet. POST\-Anforderungen sind schwieriger zu erstellen als GET\-Anforderungen, sie werden jedoch nicht zwischengespeichert. Verwenden Sie POST\-Anforderungen für alle Vorgänge, bei denen keine Zwischenspeicherung benötigt wird.  
  
```  
[ServiceContract(Namespace = "PostAjaxService")]  
    public interface ICalculator  
    {        [WebInvoke]  
        double Add(double n1, double n2);  
        //Other operations omitted…  
    }  
  
```  
  
 Erstellen Sie im Dienst mithilfe von <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> einen AJAX\-Endpunkt wie im Beispiel "Einfacher AJAX\-Dienst".  
  
 Im Gegensatz zu GET\-Anforderungen können Sie POST\-Dienste nicht aus dem Browser aufrufen. Das Navigieren zu http:\/\/localhost\/ServiceModelSamples\/service.svc\/Add?n1\=100&n2\=200 führt beispielsweise zu einem Fehler, da der POST\-Dienst erwartet, dass der `n1`\-Parameter und der `n2`\-Parameter im Nachrichtentext \(im JSON\-Format\) und nicht in der URL gesendet werden.  
  
 Die Clientwebseite "PostAjaxClientPage.aspx" enthält ASP.NET\-Code zum Aufrufen des Diensts, wenn der Benutzer auf eine der Vorgangsschaltflächen auf der Seite klickt. Der Dienst antwortet auf die gleiche Weise wie im Beispiel [Einfacher AJAX\-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) mit der GET\-Anforderung.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) und Windows Workflow Foundation \(WF\) Samples für .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie die Setupanweisungen [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausführen.  
  
2.  Erstellen Sie die Projektmappe „PostAjaxService.sln“, wie in [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) beschrieben.  
  
3.  Navigieren Sie zu http:\/\/localhost\/ServiceModelSamples\/PostAjaxClientPage.aspx \(öffnen Sie "PostAjaxClientPage.aspx" nicht aus dem Projektverzeichnis im Browser\).  
  
## Siehe auch