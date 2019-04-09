---
title: AJAX-Dienst ohne Konfiguration
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: 0a8c75136af728c2110affe224fe8bf6c47fc1eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191782"
---
# <a name="ajax-service-without-configuration"></a>AJAX-Dienst ohne Konfiguration
Dieses Beispiel veranschaulicht, wie Windows Communication Foundation (WCF) zum Erstellen eines einfachen (ASP.NET Asynchronous JavaScript and XML (AJAX)-Diensts (ein Dienst, die Sie mithilfe von JavaScript-Codes über einen Webbrowserclient zugreifen können) ohne Konfiguration Einstellungen. Der Dienst verwendet eine besondere Syntax in der .svc-Datei zur automatischen Aktivierung eines AJAX-Endpunkts.  
  
 AJAX-Unterstützung in WCF ist optimiert für die Verwendung mit ASP.NET AJAX über das `ScriptManager` Steuerelement. Ein Beispiel der Verwendung von WCF mit ASP.NET AJAX finden Sie unter den [Ajax-Beispielen](ajax.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel basiert auf dem Beispiel "AJAX-Dienst mit HTTP POST". Siehe die [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> wird verwendet, um den Dienst zu hosten.  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> Fügt automatisch eine <xref:System.ServiceModel.Description.WebScriptEndpoint> an den Dienst. Wenn keine Konfigurationsänderungen am Endpunkt vorgenommen werden müssen, kann der Abschnitt `<system.ServiceModel>` vollständig aus der Datei "Web.config" für den Dienst entfernt werden. Die Datei Web.config enthält einige ASP.NET-Einstellungen, die von ConfigFreeClientPage.aspx verwendet werden. Wenn dies nicht der Fall wäre, könnte die gesamte Datei Web.config entfernt werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie die setupanweisungen in ausführen [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Erstellen Sie die Lösung ConfigFreeAjaxService.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Navigieren Sie zu `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (Öffnen Sie ConfigFreeClientPage.aspx nicht im Browser aus dem Projektverzeichnis).  
  
> [!NOTE]
>  Stellen Sie bei der Ausführung dieses Beispiels sicher, dass für den Ordner ServiceModelSamples in IIS nicht gleichzeitig anonyme Authentifizierung und Windows-Authentifizierung aktiviert ist. Wenn das der Fall ist, deaktivieren Sie die Windows-Authentifizierung. Sobald Sie das Beispiel ausgeführt haben, aktivieren Sie die Windows-Authentifizierung und führen "iisreset" aus.  
  
## <a name="see-also"></a>Siehe auch

- [Einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
