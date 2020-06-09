---
title: ASP.NET-Zwischenspeicherungsintegration
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: c541f3caad8a500b9fdb33d00b58706bac876e37
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594750"
---
# <a name="aspnet-caching-integration"></a>ASP.NET-Zwischenspeicherungsintegration

In diesem Beispiel wird gezeigt, wie der ASP.NET-Ausgabecache mit dem WCF-WEB HTTP-Programmiermodell verwendet wird. Dieses Thema befasst sich mit den Integrationsfunktion des ASP.NET-Ausgabecaches.

## <a name="demonstrates"></a>Zeigt

Integration in den ASP.NET-Ausgabecache

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`

## <a name="discussion"></a>Diskussion

Im Beispiel wird der verwendet <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> , um das ASP.net-Ausgabe Caching mit dem Windows Communication Foundation (WCF)-Dienst zu nutzen. Das <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> wird auf Dienstvorgänge angewendet und gibt den Namen eines Cacheprofils in einer Konfigurationsdatei an, die auf Antworten vom angegebenen Vorgang angewendet werden soll.

In der Service.cs-Datei des Beispiel Dienst Projekts `GetCustomer` sind der-Vorgang und der- `GetCustomers` Vorgang mit dem gekennzeichnet <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> , der den Cache Profilnamen "CacheFor60Seconds" bereitstellt. In der Datei "Web. config" des Dienst Projekts wird das Cache Profil "CacheFor60Seconds" unter dem < `caching` >-Element von < `system.web` > bereitgestellt. Für dieses Cache Profil lautet der Wert des `duration` Attributs "60", sodass die diesem Profil zugeordneten Antworten für 60 Sekunden im ASP.net-Ausgabe Cache zwischengespeichert werden. Außerdem wird für dieses Cache Profil das- `varmByParam` Attribut auf "Format" festgelegt, sodass Anforderungen mit unterschiedlichen Werten für den `format` Abfrage Zeichen folgen Parameter separat zwischengespeichert werden. Schließlich wird das-Attribut des Cache Profils `varyByHeader` auf "Accept" festgelegt, sodass Anforderungen mit unterschiedlichen Accept-Header Werten separat zwischengespeichert werden.

Program.cs im Clientprojekt zeigt, wie ein Client dieser Art mit <xref:System.Net.HttpWebRequest> erstellt werden kann. Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen WCF-Dienst darstellt. Es ist auch möglich, über andere .NET Framework Klassen wie die WCF-Kanalfactory und auf den Dienst zuzugreifen <xref:System.Net.WebClient> . Andere Beispiele im SDK (z. b. das Beispiel für den [grundlegenden HTTP-Dienst](basic-http-service.md) ) veranschaulichen, wie diese Klassen verwendet werden, um mit einem WCF-Dienst zu kommunizieren.

## <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus

Das Beispiel umfasst drei Projekte:

- **Service**: ein Webanwendungs Projekt, das einen in ASP.net gehosteten WCF-HTTP-Dienst enthält.

- **Client**: ein Konsolen Anwendungsprojekt, das Aufrufe an den Dienst ausführt.

- **Common**: eine freigegebene Bibliothek, die den vom Client und Dienst verwendeten Customer-Typ enthält.

Während die Clientkonsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.

#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus

1. Öffnen Sie die Projektmappe für das Beispiel der Integration von ASP.NET-Zwischenspeicherung.

2. Drücken Sie STRG+UMSCH+B, um die Lösung zu erstellen.

3. Wenn das **Projektmappen-Explorer** Fenster nicht bereits geöffnet ist, drücken Sie STRG + W + S.

4. Klicken Sie im **Projektmappen-Explorer** Fenster mit der rechten Maustaste auf das **Dienst** Projekt, und wählen Sie **neue Instanz starten**aus. Der ASP.NET-Entwicklungsserver, der den Dienst hostet, wird gestartet.

5. Klicken Sie im **Projektmappen-Explorer** Fenster mit der rechten Maustaste auf das **Client** Projekt, und wählen Sie **neue Instanz starten**aus.

6. Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt. Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.

7. Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.

8. Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.

9. Drücken Sie UMSCHALT+F5, um das Debugging des Diensts zu beenden.

10. Klicken Sie im Windows-Benachrichtigungsbereich mit der rechten Maustaste auf das ASP.NET Development Server-Symbol, **und wählen Sie**dann
