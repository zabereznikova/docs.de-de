---
title: "SOAP- und HTTP-Endpunkte | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# SOAP- und HTTP-Endpunkte
In diesem Beispiel wird veranschaulicht, wie ein RPC\-basierter Dienst implementiert und im SOAP\-Format und POX\-Format \(Plain Old XML\) mit dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Webprogrammiermodell verfügbar gemacht wird.  Weitere Informationen zur HTTP\-Bindung für den Dienst finden Sie unter [Einfacher HTTP\-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md).  Dieses Beispiel befasst sich mit den Details der Bereitstellung des gleichen Diensts über SOAP und HTTP, allerdings mit unterschiedlichen Bindungen.  
  
## Veranschaulicht  
 Die Bereitstellung eines RPC\-Diensts über SOAP und HTTP mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]  
  
## Diskussion  
 Dieses Beispiel besteht aus zwei Komponenten: einem Webanwendungsprojekt \(Dienst\), das einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst enthält, und einer Konsolenanwendung \(Client\), mit dem Dienstvorgänge mit SOAP\- und HTTP\-Bindungen aufgerufen werden.  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst macht 2 Vorgänge verfügbar – `GetData` und `PutData` –, die die als Eingabe übergebene Zeichenfolge wiederholen.  Die Dienstvorgänge werden mit <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> kommentiert.  Diese Attribute steuern die HTTP\-Projektion dieser Vorgänge.  Außerdem werden sie mit <xref:System.ServiceModel.OperationContractAttribute> kommentiert, sodass sie über SOAP\-Bindungen verfügbar gemacht werden können.  Die `PutData`\-Methode des Diensts löst eine <xref:System.ServiceModel.Web.WebFaultException> aus, die mithilfe des HTTP\-Statuscodes über HTTP zurückgesendet und als SOAP\-Fehler über SOAP zurückgesendet wird.  
  
 Mit der Datei Web.config wird der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst mit 3 Endpunkten konfiguriert:  
  
-   Der ~\/service.svc\/mex\-Endpunkt, der die Dienstmetadaten für den Zugriff durch SOAP\-basierte Clients verfügbar macht.  
  
-   Der ~\/service.svc\/http\-Endpunkt, der es Clients ermöglicht, über die HTTP\-Bindung auf den Dienst zuzugreifen.  
  
-   Der ~\/service.svc\/soap\-Endpunkt, der es den Clients ermöglicht, über die SOAP über HTTP\-Bindung auf den Dienst zuzugreifen.  
  
 Der HTTP\-Endpunkt wird mit einem \<`webHttp`\>\-Standardendpunkt konfiguriert, bei dem `helpEnabled` auf `true` festgelegt wurde.  Als Ergebnis stellt der Dienst eine XHTML\-basierte Hilfeseite unter ~\/service.svc\/http\/help bereit, mit der HTTP\-basierte Clients auf den Dienst zugreifen können.  
  
 Das Clientprojekt veranschaulicht den Zugriff auf den Dienst über einen SOAP\-Proxy \(generiert durch **Dienstverweis hinzufügen**\) und den Zugriff auf den Dienst mit <xref:System.Net.WebClient>.  
  
 Das Beispiel besteht aus einem im Web gehosteten Dienst und einer Konsolenanwendung.  Während die Konsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe für das Beispiel mit den SOAP\- und HTTP\-Endpunkten.  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Wenn das Fenster noch nicht geöffnet ist, drücken Sie STRG\+W, S, um das Fenster des **Projektmappen\-Explorers** zu öffnen.  
  
4.  Klicken Sie im Fenster des **Projektmappen\-Explorers** mit der rechten Maustaste auf das Dienstprojekt, und setzen Sie den Cursor über die Option **Debuggen** im Kontextmenü, damit das Kontextmenü **Neue Instanz starten** angezeigt wird.  Klicken Sie auf **Neue Instanz starten**.  Der ASP.NET\-Entwicklungsserver, der den Dienst hostet, wird gestartet.  
  
5.  Klicken Sie im Fenster des **Projektmappen\-Explorers** mit der rechten Maustaste auf das Clientprojekt, und setzen Sie den Cursor über die Option Debuggen im Kontextmenü, damit das Kontextmenü Neue Instanz starten angezeigt wird.  Klicken Sie auf **Neue Instanz starten**.  
  
6.  Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML\-Hilfeseite für den ausgeführten Dienst angezeigt.  Sie können die HTML\-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.  
  
7.  Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.  
  
8.  Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.  
  
9. Drücken Sie UMSCHALT\+F5, um das Debugging des Diensts zu beenden.  
  
10. Klicken Sie im Windows\-Infobereich mit der rechten Maustaste auf das Symbol des ASP.NET\-Entwicklungsservers, und wählen Sie aus dem Kontextmenü die Option **Beenden** aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`