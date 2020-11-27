---
title: Implementieren eines Suchproxys
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: ae003c89bb0f14623c5d31a1596533d821380336
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268299"
---
# <a name="implementing-a-discovery-proxy"></a>Implementieren eines Suchproxys

In diesem Thema werden die Schritte beschrieben, die zum Implementieren eines Suchproxys erforderlich sind. Ein Suchproxy ist ein eigenständiger Dienst, der ein Repository mit Diensten enthält. Clients können einen Suchproxy abfragen, um nach erkennbaren Diensten, die für den Proxy verfügbar sind. Die Art und Weise, wie ein Proxy mit Diensten aufgefüllt wird, hängt von der Implementierung ab. Ein Suchproxy kann z. B. eine Verbindung zu einem vorhandenen Dienstrepository herstellen und diese Informationen erkennbar machen, ein Administrator kann einem Proxy erkennbare Dienste mithilfe einer Verwaltungs-API hinzufügen, oder ein Suchproxy kann seinen internen Cache mithilfe der Ankündigungsfunktionalität aktualisieren.  
  
 Die WCF-Implementierung stellt Basisklassen bereit, mit denen problemlos ein Proxy erstellt werden kann. Sie können mit diesen APIs einen Suchproxy für das vorhandene Repository erstellen.  
  
 Der hier implementierte Suchproxy gleicht allen anderen WCF-Diensten. Sie können den Suchproxy auch erkennbar machen und die Clients nach seinen Endpunkten suchen lassen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Vorgehensweise: Implementieren eines Suchproxys](how-to-implement-a-discovery-proxy.md)  
 Beschreibt, wie Sie einen Suchproxy implementieren.  
  
 [Vorgehensweise: Implementieren eines ermittelbaren Diensts, der beim Suchproxy registriert ist](discoverable-service-that-registers-with-the-discovery-proxy.md)  
 Beschreibt, wie ein erkennbarer WCF-Dienst implementiert wird, der beim suchproxy registriert wird.  
  
 [Vorgehensweise: Implementieren einer Clientanwendung, die den Suchproxy zum Suchen nach einem Dienst verwendet](client-app-discovery-proxy-to-find-a-service.md)  
 Beschreibt, wie eine WCF-Client Anwendung implementiert wird, die den suchproxy zum Suchen nach einem Dienst verwendet.  
  
 [Vorgehensweise: Testen des Suchproxys](how-to-test-the-discovery-proxy.md)  
 Beschreibt, wie Sie den Code testen, den Sie in den vorherigen drei Themen geschrieben haben.  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF-Suche](wcf-discovery.md)
- [Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
