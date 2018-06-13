---
title: ASP.NET-Zwischenspeicherungsintegration
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: 744ecbff8b51565906ff4c619ba8c8aecff123c7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805407"
---
# <a name="aspnet-caching-integration"></a>ASP.NET-Zwischenspeicherungsintegration
In diesem Beispiel wird gezeigt, wie der ASP.NET-Ausgabecache mit dem WCF-WEB HTTP-Programmiermodell verwendet wird. Finden Sie unter der [grundlegenden Ressourcendiensts](../../../../docs/framework/wcf/samples/basic-resource-service.md) Beispiel eine selbst gehostete Version dieses Szenarios, die die dienstimplementierung ausführlich erläutert wird. Dieses Thema befasst sich mit den Integrationsfunktion des ASP.NET-Ausgabecaches.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Integration in den ASP.NET-Ausgabecache  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a>Diskussion  
 Das Beispiel verwendet die <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> ASP.NET nutzen Ausgabecaches, mit der Windows Communication Foundation (WCF)-Dienst. Das <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> wird auf Dienstvorgänge angewendet und gibt den Namen eines Cacheprofils in einer Konfigurationsdatei an, die auf Antworten vom angegebenen Vorgang angewendet werden soll.  
  
 In der Datei Service.cs des Beispielprojekts Dienst sowohl den `GetCustomer` und `GetCustomers` Vorgänge sind mit markierten der <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, stellt den cacheprofilnamen "CacheFor60Seconds". In der Datei "Web.config" des Dienstprojekts wird das Cacheprofil "CacheFor60Seconds" bereitgestellt, unter dem <`caching`> Element des <`system.web`>. Für dieses Cacheprofil wird der Wert der `duration` -Attribut ist "60", dieses Profil zugeordnete Antworten 60 Sekunden lang im ASP.NET-Ausgabecache zwischengespeichert werden. Für dieses Cacheprofil der `varmByParam` -Attribut festgelegt ist; bei Anforderungen mit anderen Werten für "formatieren" der `format` -Abfragezeichenfolgenparameter die Antworten getrennt zwischengespeichert. Abschließend wird des Cacheprofils des `varyByHeader` -Attribut auf "Akzeptieren" festgelegt ist, müssen Anforderungen mit anderen Accept-Headerwerten getrennt zwischengespeichert werden.  
  
 Program.cs im Clientprojekt zeigt, wie ein Client dieser Art mit <xref:System.Net.HttpWebRequest> erstellt werden kann. Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen WCF-Dienst darstellt. Es ist auch möglich, die Zugriff auf den Dienst mit anderen .NET Framework-Klassen wie der WCF-Kanalfactory und <xref:System.Net.WebClient>. Weitere Beispiele im SDK (z. B. die [grundlegenden HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) Beispiel und die [automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md) Beispiel) veranschaulicht, wie diese Klassen verwenden, um die Kommunikation mit einem WCF-Dienst.  
  
## <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
 Das Beispiel umfasst drei Projekte:  
  
-   **Dienst**: ein Webanwendungsprojekt, der einen gehosteten WCF-HTTP-Dienst in ASP.NET enthält.  
  
-   **Client**: ein Konsolenanwendungsprojekt, das Aufrufe an den Dienst ausführt.  
  
-   **Allgemeine**: eine freigegebene Bibliothek, die die vom Client und Dienst verwendeten Kundentyp enthält.  
  
 Während die Clientkonsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe für das Beispiel der Integration von ASP.NET-Zwischenspeicherung.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Wenn die **Projektmappen-Explorer** Fenster nicht bereits geöffnet ist, drücken Sie STRG + W + s.  
  
4.  Aus der **Projektmappen-Explorer** Fenster, mit der rechten Maustaste die **Service** Projekt, und wählen Sie **neue Instanz starten**. Der ASP.NET-Entwicklungsserver, der den Dienst hostet, wird gestartet.  
  
5.  Aus der **Projektmappen-Explorer** Fenster, mit der rechten Maustaste die **Client** Projekt, und wählen Sie **neue Instanz starten**.  
  
6.  Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt. Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.  
  
7.  Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.  
  
8.  Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.  
  
9. Drücken Sie UMSCHALT+F5, um das Debugging des Diensts zu beenden.  
  
10. Klicken Sie im Windows-Infobereich mit der rechten Maustaste, klicken Sie auf das Symbol "ASP.NET Development Server", und wählen **beenden**.
