---
title: SOAP- und HTTP-Endpunkte
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d122512a16a0959d60bfa658d96aa87a52e40299
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="soap-and-http-endpoints"></a>SOAP- und HTTP-Endpunkte
In diesem Beispiel wird veranschaulicht, wie ein RPC-basierter Dienst implementiert und im SOAP-Format verfügbar gemacht und die "Plain Old XML" (POX) formatieren Sie mit der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Webprogrammiermodell. Finden Sie unter der [grundlegenden HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) Sample detaillierte Informationen über die HTTP-Bindung für den Dienst. Dieses Beispiel befasst sich mit den Details der Bereitstellung des gleichen Diensts über SOAP und HTTP, allerdings mit unterschiedlichen Bindungen.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Die Bereitstellung eines RPC-Diensts über SOAP und HTTP mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]  
  
## <a name="discussion"></a>Diskussion  
 Dieses Beispiel besteht aus zwei Komponenten: einem Webanwendungsprojekt (Dienst), das einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst enthält, und einer Konsolenanwendung (Client), mit dem Dienstvorgänge mit SOAP- und HTTP-Bindungen aufgerufen werden.  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst macht 2 Vorgänge verfügbar – `GetData` und `PutData` –, die die als Eingabe übergebene Zeichenfolge wiederholen. Die Dienstvorgänge werden mit <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> kommentiert. Diese Attribute steuern die HTTP-Projektion dieser Vorgänge. Außerdem werden sie mit <xref:System.ServiceModel.OperationContractAttribute> kommentiert, sodass sie über SOAP-Bindungen verfügbar gemacht werden können. Die `PutData`-Methode des Diensts löst eine <xref:System.ServiceModel.Web.WebFaultException> aus, die mithilfe des HTTP-Statuscodes über HTTP zurückgesendet und als SOAP-Fehler über SOAP zurückgesendet wird.  
  
 Mit der Datei Web.config wird der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst mit 3 Endpunkten konfiguriert:  
  
-   Der ~/service.svc/mex-Endpunkt, der die Dienstmetadaten für den Zugriff durch SOAP-basierte Clients verfügbar macht.  
  
-   Der ~/service.svc/http-Endpunkt, der es Clients ermöglicht, über die HTTP-Bindung auf den Dienst zuzugreifen.  
  
-   Der ~/service.svc/soap-Endpunkt, der es den Clients ermöglicht, über die SOAP über HTTP-Bindung auf den Dienst zuzugreifen.  
  
 Der HTTP-Endpunkt wird mit einem <`webHttp`>-Standardendpunkt konfiguriert, bei dem `helpEnabled` auf `true` festgelegt wurde. Als Ergebnis stellt der Dienst eine XHTML-basierte Hilfeseite unter ~/service.svc/http/help bereit, mit der HTTP-basierte Clients auf den Dienst zugreifen können.  
  
 Das Clientprojekt veranschaulicht den Zugriff auf den Dienst über einen SOAP-Proxy (generiert durch **Hinzufügen eines Dienstverweises**) und den Zugriff auf den Dienst mit <xref:System.Net.WebClient>.  
  
 Das Beispiel besteht aus einem im Web gehosteten Dienst und einer Konsolenanwendung. Während die Konsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe für das Beispiel mit den SOAP- und HTTP-Endpunkten.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Wenn es nicht bereits geöffnet ist, drücken Sie STRG + W, S, öffnen Sie die **Projektmappen-Explorer** Fenster.  
  
4.  Aus der **Projektmappen-Explorer** Fenster mit der rechten Maustaste die **Service** Projekt, und platzieren Sie den Cursor über die **Debuggen** Kontextmenüoption, damit die **neue starten Instanz** Kontextmenü wird angezeigt. Klicken Sie auf **neue Instanz starten**. Der ASP.NET-Entwicklungsserver, der den Dienst hostet, wird gestartet.  
  
5.  Aus dem Projektmappen-Explorer-Fenster mit der rechten Maustaste des Clientprojekts, und platzieren Sie den Cursor über die **Debuggen** Kontextmenüoption, damit die **neue Instanz starten** Kontextmenü wird angezeigt. Klicken Sie auf **neue Instanz starten**.  
  
6.  Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt. Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.  
  
7.  Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.  
  
8.  Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.  
  
9. Drücken Sie UMSCHALT+F5, um das Debugging des Diensts zu beenden.  
  
10. Klicken Sie im Windows-Infobereich mit der rechten Maustaste des Symbol "ASP.NET Development Server", und wählen **beenden** aus dem Kontextmenü.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
