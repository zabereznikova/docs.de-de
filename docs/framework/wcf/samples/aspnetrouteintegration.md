---
title: "AspNetRouteIntegration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0638ce0e-d053-47df-a447-688e447a03fb
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# AspNetRouteIntegration
In diesem Beispiel wird veranschaulicht, wie ein [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST\-Dienst mit ASP.NET\-Routen gehostet wird.Im [Einfacher Ressourcendienst](../../../../docs/framework/wcf/samples/basic-resource-service.md)\-Beispiel wird eine selbst gehostete Version dieses Szenarios veranschaulicht und die Dienstimplementierung eingehend erläutert.In diesem Thema steht die ASP.NET\-Integrationsfunktion im Vordergrund.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu ASP.NET\-Routing finden Sie unter <xref:System.Web.Routing>.  
  
## Beispieldetails  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst macht eine Auflistung der Kunden auf ressourcenorientierte\/REST\-Weise verfügbar.Wie ein SOAP\-basierter [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst kann der Dienst in ASP.NET mithilfe einer SVC\-Datei gehostet werden.Diese Vorgehensweise empfiehlt sich in HTTP\-Szenarien jedoch häufig nicht, da sie erfordert, dass die URL für den Dienst .svc enthält.Darüber hinaus muss dafür eine SVC\-Datei mit der Dienstbibliothek bereitgestellt werden.Diese Einschränkungen lassen sich vermeiden, wenn der Dienst mit ASP.NET\-Routen gehostet wird, wie in diesem Beispiel gezeigt.  
  
 Im Beispiel wird der Dienst in ASP.NET gehostet, indem <xref:System.ServiceModel.Activation.ServiceRoute> in einer Global.asax\-Datei hinzugefügt wird.Die <xref:System.ServiceModel.Activation.ServiceRoute> gibt den Typ des Diensts \(in diesem Fall 'Service'\), den Typ der für diesen Dienst zu verwendenden Diensthostfactory \(in diesem Fall <xref:System.ServiceModel.Activation.WebServiceHostFactory>\) und die HTTP\-Basisadresse für den Dienst \(in diesem Fall '~\/Customers’\) an.  
  
 Außerdem umfasst das Beispiel eine Web.config\-Datei, die das <xref:System.Web.Routing.UrlRoutingModule> hinzufügt \(um ASP.NET\-Routen zu aktivieren\) und die Konfiguration für den Dienst enthält.Die Konfiguration konfiguriert insbesondere den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst mit einem standardmäßigen <xref:System.ServiceModel.Description.WebHttpEndpoint>, für den die <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A>\-Einstellung auf `true` festgelegt ist.Daraufhin erstellt die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Infrastruktur eine automatische HTML\-basierte Hilfeseite unter `http://localhost/Customers/help`, die Informationen dazu bereitstellt, wie HTTP\-Anforderungen an den Dienst erstellt werden und wie auf die HTTP\-Antwort des Diensts – z. B. die Darstellung der Kundendetails in XML und JSON – zugegriffen werden kann.  
  
 Indem der Client die Kundenauflistung \(und, allgemeiner ausgedrückt, jede Ressource\) auf diese Weise verfügbar macht, kann er mithilfe von URIs sowie HTTP `GET`, `PUT`, `DELETE` und `POST` auf einheitliche Weise mit einem Dienst interagieren.  
  
 Program.cs im Clientprojekt zeigt, wie ein Client dieser Art mit <xref:System.Net.HttpWebRequest> erstellt werden kann.Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst darstellt.Es ist auch möglich, mit anderen .NET Framework\-Klassen wie der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Kanalfactory und <xref:System.Net.WebClient> auf den Dienst zuzugreifen.In anderen Beispielen im SDK \(z. B. [Einfacher HTTP\-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) und [Automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md)\) wird gezeigt, wie diese Klassen verwendet werden, um mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst zu kommunizieren.  
  
 Dieses Beispiel besteht aus drei Projekten:  
  
 Dienst  
 Ein Webanwendungsprojekt einschließlich WCF\-HTTP\-Dienst, der in ASP.NET gehostet wird.  
  
 Client  
 Ein Konsolenanwendungsprojekt, das Aufrufe an den Dienst ausführt.  
  
 Allgemein  
 Eine freigegebene Bibliothek, die den vom Client und vom Dienst verwendeten `Customer`\-Typ enthält.Während die Clientkonsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappe für das Beispiel der ASP.NET\-Routenintegration in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Wenn das Fenster noch nicht geöffnet ist, drücken Sie “STRG\+W, S”, um das Fenster des **Projektmappen\-Explorers** zu öffnen.  
  
4.  Klicken Sie im Fenster des **Projektmappen\-Explorers** mit der rechten Maustaste auf das Dienstprojekt, und setzen Sie den Cursor im Kontextmenü über die Option **Debuggen**, damit das Kontextmenü **Neue Instanz starten** angezeigt wird. Klicken Sie anschließend auf **Neue Instanz starten**.Der ASP.NET\-Entwicklungsserver, der den Dienst hostet, wird gestartet.  
  
5.  Klicken Sie im Fenster des **Projektmappen\-Explorers** mit der rechten Maustaste auf das Clientprojekt, und setzen Sie den Cursor im Kontextmenü über die Option **Debuggen**, damit das Kontextmenü **Neue Instanz starten** angezeigt wird. Klicken Sie anschließend auf **Neue Instanz starten**.  
  
6.  Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML\-Hilfeseite für den ausgeführten Dienst angezeigt.Sie können die HTML\-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.  
  
7.  Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.  
  
8.  Drücken Sie UMSCHALT\+F5, um das Debuggen des Diensts zu beenden, klicken Sie im Windows\-Infobereich mit der rechten Maustaste auf das Symbol für den ASP.NET\-Entwicklungsserver, und wählen Sie im Kontextmenü **Beenden** aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetRouteIntegration`  
  
## Siehe auch