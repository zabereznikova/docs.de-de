---
title: "AJAX-Dienst ohne Konfiguration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# AJAX-Dienst ohne Konfiguration
In diesem Beispiel wird die Verwendung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zum Erstellen eines grundlegenden AJAX\-Diensts \(ASP.NET Asynchronous JavaScript and XML\) ohne Verwendung von Konfigurationseinstellungen beschrieben. Ein AJAX\-Dienst ist ein Dienst, auf den Sie durch die Verwendung eines JavaScript\-Codes über einen Webbrowserclient zugreifen können.  Der Dienst verwendet eine besondere Syntax in der .svc\-Datei zur automatischen Aktivierung eines AJAX\-Endpunkts.  
  
 Die AJAX\-Unterstützung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist für die Verwendung mit ASP.NET AJAX über das `ScriptManager`\-Steuerelement optimiert.  Ein Beispiel für das Verwenden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit ASP.NET AJAX finden Sie unter [Ajax Samples](http://msdn.microsoft.com/de-de/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel basiert auf dem Beispiel "AJAX\-Dienst mit HTTP POST".  Wie im Beispiel [Einfacher AJAX\-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) beschrieben, wird <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> zum Hosten des Dienstes verwendet.  
  
```  
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
  
```  
  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> fügt dem Dienst automatisch einen <xref:System.ServiceModel.Description.WebScriptEndpoint> hinzu.  Wenn keine Konfigurationsänderungen am Endpunkt vorgenommen werden müssen, kann der Abschnitt \<system.ServiceModel\> vollständig aus der Datei "Web.config" für den Dienst entfernt werden.  Die Datei Web.config enthält einige ASP.NET\-Einstellungen, die von ConfigFreeClientPage.aspx verwendet werden.  Wenn dies nicht der Fall wäre, könnte die gesamte Datei Web.config entfernt werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Führen Sie unbedingt die Setupanweisungen in [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) aus.  
  
2.  Erstellen Sie die Lösung ConfigFreeAjaxService.sln, wie in [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) beschrieben.  
  
3.  Navigieren Sie zu http:\/\/localhost\/ServiceModelSamples\/ConfigFreeClientPage.aspx \(öffnen Sie ConfigFreeClientPage.aspx im Browser nicht aus dem Projektverzeichnis\).  
  
> [!NOTE]
>  Stellen Sie bei der Ausführung dieses Beispiels sicher, dass für den Ordner ServiceModelSamples in IIS nicht gleichzeitig anonyme Authentifizierung und Windows\-Authentifizierung aktiviert ist.  Wenn das der Fall ist, deaktivieren Sie die Windows\-Authentifizierung.  Sobald Sie das Beispiel ausgeführt haben, aktivieren Sie die Windows\-Authentifizierung und führen "iisreset" aus.  
  
## Siehe auch  
 [Einfacher AJAX\-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md)