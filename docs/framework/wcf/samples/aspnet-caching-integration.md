---
title: "ASP.NET-Zwischenspeicherungsintegration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ASP.NET-Zwischenspeicherungsintegration
In diesem Beispiel wird gezeigt, wie der ASP.NET\-Ausgabecache mit dem WCF\-WEB HTTP\-Programmiermodell verwendet wird.  Eine selbst gehostete Version dieses Szenarios finden Sie im Beispiel [Einfacher Ressourcendienst](../../../../docs/framework/wcf/samples/basic-resource-service.md), in dem die Dienstimplementierung eingehend erläutert wird.  Dieses Thema befasst sich mit den Integrationsfunktion des ASP.NET\-Ausgabecaches.  
  
## Veranschaulicht  
 Integration in den ASP.NET\-Ausgabecache  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## Diskussion  
 Im Beispiel wird das <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> verwendet, um den ASP.NET\-Ausgabecache mit dem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienst nutzen zu können.  Das <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> wird auf Dienstvorgänge angewendet und gibt den Namen eines Cacheprofils in einer Konfigurationsdatei an, die auf Antworten vom angegebenen Vorgang angewendet werden soll.  
  
 In der Datei Service.cs des Beispieldienstprojekts werden der `GetCustomer`\-Vorgang und der `GetCustomers`\-Vorgang mit dem <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> markiert, das den Cacheprofilnamen "CacheFor60Seconds" angibt.  In der Datei "Web.config" des Dienstprojekts wird das Cacheprofil "CacheFor60Seconds" unter dem \<`caching`\>\-Element von \<`system.web`\> bereitgestellt.  Für dieses Cacheprofil beträgt der Wert des `duration`\-Attributs "60". Deshalb werden diesem Profil zugeordnete Antworten 60 Sekunden lang im ASP.NET\-Ausgabecache zwischengespeichert.  Auch für dieses Cacheprofil wird das `varmByParam`\-Attribut auf "format" festgelegt; bei Anforderungen mit anderen Werten für den `format`\-Abfragezeichenfolgenparameter werden die Antworten getrennt zwischengespeichert.  Schließlich wird das `varyByHeader`\-Attribut des Profils auf "Accept" festgelegt, sodass Anforderungen mit anderen Accept\-Headerwerten getrennt zwischengespeichert werden.  
  
 Program.cs im Clientprojekt zeigt, wie ein Client dieser Art mit <xref:System.Net.HttpWebRequest> erstellt werden kann.  Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen WCF\-Dienst darstellt.  Es ist auch möglich, mit anderen .NET Framework\-Klassen wie der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Kanalfactory und <xref:System.Net.WebClient> auf den Dienst zuzugreifen.  In anderen Beispielen im SDK \(z. B. [Einfacher HTTP\-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) und [Automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md)\) wird gezeigt, wie diese Klassen verwendet werden, um mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst zu kommunizieren.  
  
## So führen Sie das Beispiel aus  
 Das Beispiel umfasst drei Projekte:  
  
-   **Service**: Ein Webanwendungsprojekt einschließlich WCF\-HTTP\-Dienst, der in ASP.NET gehostet wird.  
  
-   **Client**: Ein Konsolenanwendungsprojekt, das Aufrufe an den Dienst ausführt.  
  
-   **Common**: Eine freigegebene Bibliothek, die den vom Client und Dienst verwendeten Kundentyp enthält.  
  
 Während die Clientkonsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe für das Beispiel der Integration von ASP.NET\-Zwischenspeicherung.  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Wenn das Fenster **Projektmappen\-Explorer** noch nicht geöffnet ist, drücken Sie STRG\+W\+S.  
  
4.  Klicken Sie im Fenster **Projektmappen\-Explorer** mit der rechten Maustaste auf das Dienstprojekt, und wählen Sie **Neue Instanz starten** aus.  Der ASP.NET\-Entwicklungsserver, der den Dienst hostet, wird gestartet.  
  
5.  Klicken Sie im Fenster **Projektmappen\-Explorer** mit der rechten Maustaste auf das Clientprojekt, und wählen Sie **Neue Instanz starten** aus.  
  
6.  Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML\-Hilfeseite für den ausgeführten Dienst angezeigt.  Sie können die HTML\-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.  
  
7.  Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.  
  
8.  Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.  
  
9. Drücken Sie UMSCHALT\+F5, um das Debugging des Diensts zu beenden.  
  
10. Klicken Sie im Windows\-Infobereich mit der rechten Maustaste auf das ASP.NET\-Entwicklungsserversymbol, und wählen Sie **Beenden** aus.