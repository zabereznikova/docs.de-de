---
title: 'Vorgehensweise: Testen des Suchproxys'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 78921d0a26f1116c87c2931b1472a161d6fed145
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592813"
---
# <a name="how-to-test-the-discovery-proxy"></a>Vorgehensweise: Testen des Suchproxys
Dies ist das vierte von vier Themen, in denen beschrieben wird, wie Sie einen Suchproxy implementieren. Im vorherigen Thema Gewusst [wie: Implementieren einer Client Anwendung, die den suchproxy zum Suchen nach einem Dienst verwendet](client-app-discovery-proxy-to-find-a-service.md), haben Sie eine WCF-Client Anwendung implementiert, die den suchproxy zum Suchen nach einem Dienst verwendet und dann den Dienst aufruft. In diesem Thema wird beschrieben, wie Sie überprüfen, ob der Suchproxy, der Dienst und die Clientanwendung ordnungsgemäß funktionieren.  
  
### <a name="run-the-discovery-proxy"></a>Ausführen des Suchproxys  
  
1. Öffnen Sie eine Eingabeaufforderung als Administrator.  
  
2. Ggf. wird ein Dialogfeld mit folgendem Hinweis angezeigt: Die Windows-Firewall hat einige Funktionen dieses Programms geblockt. Wenn diese Meldung angezeigt wird, klicken Sie auf die Schaltfläche **Sperre entsperren** .  
  
3. Führen Sie innerhalb der Eingabeaufforderung den Suchproxy "DiscoveryProxy.exe" aus.  
  
4. Die Anwendung sollte den folgenden Text anzeigen: `Proxy started. Hit Enter to exit`.  
  
### <a name="run-the-discoverable-service"></a>Ausführen des erkennbaren Diensts  
  
1. Öffnen Sie eine Eingabeaufforderung als Administrator.  
  
2. Führen Sie innerhalb der Eingabeaufforderung den erkennbaren Dienst "Service.exe" aus.  
  
3. Die Datei "DiscoveryProxy. exe" sollte den folgenden Text anzeigen: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### <a name="run-the-client-application"></a>Ausführen der Clientanwendung  
  
1. Öffnen Sie eine Eingabeaufforderung.  
  
2. Führen Sie innerhalb der Eingabeaufforderung die Anwendung "client.exe" aus.  
  
3. Nach einigen Sekunden zeigt die Clientanwendung den folgenden Text an: Verbindung mit [Dienstendpunkt] wird hergestellt.  
  
4. "service.exe" sollte dann den folgenden Text anzeigen: Begrüßungsanforderung empfangen, Antwort folgt.  
  
5. "client.exe" zeigt dann den folgenden Text an: Hello Client!  
  
### <a name="shut-down-the-applications"></a>Herunterfahren der Anwendungen  
  
1. Fahren Sie die Clientanwendung herunter.  
  
2. Beenden Sie den Dienst. Der Suchproxy zeigt den folgenden Text an: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.  
  
3. Fahren Sie den Suchproxy herunter.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die WCF-Suche](wcf-discovery-overview.md)
- [Vorgehensweise: Implementieren eines Suchproxys](how-to-implement-a-discovery-proxy.md)
- [Vorgehensweise: Implementieren eines ermittelbaren Diensts, der beim Suchproxy registriert ist](discoverable-service-that-registers-with-the-discovery-proxy.md)
- [Vorgehensweise: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet](client-app-discovery-proxy-to-find-a-service.md)
