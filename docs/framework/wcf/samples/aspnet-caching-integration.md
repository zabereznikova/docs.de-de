---
title: ASP.NET-Zwischenspeicherungsintegration
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: 56f686b83deb576f1245a9d4b9df2df433ea1e2f
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045776"
---
# <a name="aspnet-caching-integration"></a>ASP.NET-Zwischenspeicherungsintegration

In diesem Beispiel wird gezeigt, wie der ASP.NET-Ausgabecache mit dem WCF-WEB HTTP-Programmiermodell verwendet wird. Dieses Thema befasst sich mit den Integrationsfunktion des ASP.NET-Ausgabecaches.

## <a name="demonstrates"></a>Veranschaulicht

Integration in den ASP.NET-Ausgabecache

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`

## <a name="discussion"></a>Diskussion

Im Beispiel wird der <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> verwendet, um das ASP.net-Ausgabe Caching mit dem Windows Communication Foundation (WCF)-Dienst zu nutzen. Das <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> wird auf Dienstvorgänge angewendet und gibt den Namen eines Cacheprofils in einer Konfigurationsdatei an, die auf Antworten vom angegebenen Vorgang angewendet werden soll.

In der Service.cs-Datei des Beispiel Dienst Projekts sind der `GetCustomer` -Vorgang und der- `GetCustomers` Vorgang mit <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>dem gekennzeichnet, der den Cache Profilnamen "CacheFor60Seconds" bereitstellt. In der Datei "Web. config" des Dienst Projekts wird das Cache Profil "CacheFor60Seconds" unter dem <`caching`>-Element von <`system.web`> bereitgestellt. Für dieses Cache Profil lautet der Wert des `duration` Attributs "60", sodass die diesem Profil zugeordneten Antworten für 60 Sekunden im ASP.net-Ausgabe Cache zwischengespeichert werden. Außerdem wird für dieses Cache Profil das `varmByParam` -Attribut auf "Format" festgelegt, sodass Anforderungen mit unterschiedlichen Werten für den `format` Abfrage Zeichen folgen Parameter separat zwischengespeichert werden. Schließlich wird das-Attribut des `varyByHeader` Cache Profils auf "Accept" festgelegt, sodass Anforderungen mit unterschiedlichen Accept-Header Werten separat zwischengespeichert werden.

Program.cs im Clientprojekt zeigt, wie ein Client dieser Art mit <xref:System.Net.HttpWebRequest> erstellt werden kann. Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen WCF-Dienst darstellt. Es ist auch möglich, über andere .NET Framework Klassen wie die WCF-Kanalfactory und <xref:System.Net.WebClient>auf den Dienst zuzugreifen. Andere Beispiele im SDK (z. b. das Beispiel für den [grundlegenden HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) ) veranschaulichen, wie diese Klassen verwendet werden, um mit einem WCF-Dienst zu kommunizieren.

## <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus

Das Beispiel umfasst drei Projekte:

- **Dienst:** Ein Webanwendungs Projekt, das einen in ASP.net gehosteten WCF-HTTP-Dienst enthält.

- **Client**: Ein Konsolenanwendungsprojekt, das Aufrufe an den Dienst ausführt.

- **Allgemein**: Eine freigegebene Bibliothek, die den vom Client und Dienst verwendeten Customer-Typ enthält.

Während die Clientkonsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.

#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus

1. Öffnen Sie die Projektmappe für das Beispiel der Integration von ASP.NET-Zwischenspeicherung.

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

3. Wenn das **Projektmappen-Explorer** Fenster nicht bereits geöffnet ist, drücken Sie STRG + W + S.

4. Klicken Sie im **Projektmappen-Explorer** Fenster mit der rechten Maustaste auf das **Dienst** Projekt, und wählen Sie **neue Instanz starten**aus. Der ASP.NET-Entwicklungsserver, der den Dienst hostet, wird gestartet.

5. Klicken Sie im **Projektmappen-Explorer** Fenster mit der rechten Maustaste auf das **Client** Projekt, und wählen Sie **neue Instanz starten**aus.

6. Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt. Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.

7. Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.

8. Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.

9. Drücken Sie UMSCHALT+F5, um das Debugging des Diensts zu beenden.

10. Klicken Sie im Windows-Benachrichtigungsbereich mit der rechten Maustaste auf das ASP.netDevelopment Server-Symbol, und wählen Sie dann
