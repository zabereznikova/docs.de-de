---
title: Clientanwendungen mittlerer Ebene
ms.date: 03/30/2017
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
ms.openlocfilehash: 667cc98f46b131fe91e17f3b1b16af429dc597ee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174082"
---
# <a name="middle-tier-client-applications"></a>Clientanwendungen mittlerer Ebene
Dieses Thema beschreibt verschiedene Probleme bezüglich Clientanwendungen mittlerer Ebene, die Windows Communication Foundation (WCF) verwenden.  
  
## <a name="increasing-middle-tier-client-performance"></a>Verbessern der Leistung von Clients mittlerer Ebene  
 Im Vergleich zu früheren Kommunikationstechnologien wie Webdiensten unter Verwendung [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], die Erstellung einer Instanz der WCF-Client kann aufgrund der umfangreichen Funktionen von WCF komplexer sein. Beispiel: Beim Öffnen eines <xref:System.ServiceModel.ChannelFactory%601>-Objekts kann von diesem Objekt eine sichere Sitzung mit dem Dienst hergestellt werden, was zu einer Verlängerung der Startzeit der Clientinstanz führt. In der Regel wirken diese zusätzlichen Funktionen Clientanwendungen erheblich sich nicht, da die WCF-Client mehrere Aufrufe führt und dann schließt.  
  
 Clientanwendungen mittlerer Ebene, jedoch können viele WCF-Clientobjekten schnell erstellen und folglich treten höhere initialisierungsanforderungen. Für die Leistungsoptimierung von Anwendungen mittlerer Ebene beim Aufrufen von Diensten haben Sie die Wahl zwischen zwei grundsätzlichen Vorgehensweisen:  
  
-   Zwischenspeichern des WCF-Clientobjekts und bei nachfolgenden Aufrufen wiederverwendet, wenn möglich.  
  
-   Erstellen Sie eine <xref:System.ServiceModel.ChannelFactory%601> Objekt, und klicken Sie dann das Objekt zum Erstellen von neuen WCF-Clients kanalobjekten, für jeden Aufruf verwenden.  
  
 Bei diesen Vorgehensweisen sollten Sie Folgendes beachten:  
  
-   Wenn der Dienst einen clientspezifischer Zustand mithilfe einer Sitzungs verwaltet, können nicht Sie den mittleren Ebene WCF-Client mit mehreren-Clientebene Anforderungen wiederverwenden, da der Zustand des Diensts an, die von den Clients mittlerer Ebene gebunden ist.  
  
-   Wenn der Dienst über Authentifizierung pro Client-durchführen muss, müssen Sie einen neuen Client für jede eingehende Anforderung erstellen, auf der mittleren Ebene keine der WCF-Clients mittlerer Ebene (oder clientkanalobjekt WCF) nutzen, da die Anmeldeinformationen des Clients der mittleren Ebene kann nicht geändert werden, nachdem der WCF-Client (oder <xref:System.ServiceModel.ChannelFactory%601>) erstellt wurde.  
  
-   Channels und von den Channels erstellte Clients sind zwar threadsicher, unterstützen jedoch möglicherweise keine gleichzeitigen Schreibvorgänge mehrerer Nachrichten zur Übertragung. Beim Senden umfangreicher Nachrichten (und besonders beim Streaming) wird der Sendevorgang möglicherweise blockiert, da auf den Abschluss eines anderen Sendevorgangs gewartet wird. Daraus ergeben sich zwei Probleme: fehlende Parallelität und die Gefahr eines Deadlocks, wenn die Ablaufsteuerung wieder zu dem Dienst zurückkehrt, von dem der Channel wiederverwendet wird (oder mit anderen Worten: Wenn vom freigegebenen Client ein Dienst aufgerufen wird, dessen Codepfad einen Rückruf an den freigegebenen Client auslöst). Dies gilt unabhängig vom Typ des WCF-Clients, die Sie wiederverwenden.  
  
-   Fehler in Channels müssen unabhängig davon behoben werden, ob der Channel freigegeben ist. Beim Wiederverwenden von Channels kann ein fehlerhafter Channel dazu führen, dass gleich mehrere ausstehende Anforderungen oder Sendevorgänge nicht ausgeführt werden.  
  
 Ein Beispiel zur Veranschaulichung von bewährten Methoden zum Wiederverwenden eines Clients für mehrere Anforderungen finden Sie unter [Datenbindung in einem ASP.NET-Client](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md).  
  
 Darüber hinaus können Sie die Leistung beim Starten von Clients verbessern, von denen serialisierbare Datentypen verwendet werden. Für die Serialisierung dieser Datentypen wird der Serialisierungscode von <xref:System.Xml.Serialization.XmlSerializer> zum Generieren und Kompilieren zur Laufzeit verwendet, was eine Beeinträchtigung der Leistung beim Start zur Folge haben kann. Die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) können startleistung für diese Anwendungen verbessern, indem der erforderliche Serialisierungscode aus den kompilierten Assemblys für die Anwendung generiert. Weitere Informationen finden Sie unter [Vorgehensweise: Verbessern der Startzeit von WCF-Client Clientanwendungen mit dem XmlSerializer](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Siehe auch

- [Zugreifen auf Dienste mithilfe eines WCF-Clients](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)
