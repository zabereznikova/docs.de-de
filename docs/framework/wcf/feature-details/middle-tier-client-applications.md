---
title: Clientanwendungen mittlerer Ebene
ms.date: 03/30/2017
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
ms.openlocfilehash: 5019215567f4c9127f2e53fd4cdf0d4a67b84d17
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248252"
---
# <a name="middle-tier-client-applications"></a>Clientanwendungen mittlerer Ebene

In diesem Thema werden verschiedene Probleme behandelt, die spezifisch für Client Anwendungen der mittleren Ebene sind, die Windows Communication Foundation (WCF) verwenden.  
  
## <a name="increasing-middle-tier-client-performance"></a>Verbessern der Leistung von Clients mittlerer Ebene  

 Im Vergleich zu früheren Kommunikationstechnologien, wie z. b. Webdiensten mit ASP.net, kann die Erstellung einer WCF-Client Instanz aufgrund der umfangreichen Funktionsgruppe von WCF komplexer sein. Beispiel: Beim Öffnen eines <xref:System.ServiceModel.ChannelFactory%601>-Objekts kann von diesem Objekt eine sichere Sitzung mit dem Dienst hergestellt werden, was zu einer Verlängerung der Startzeit der Clientinstanz führt. In der Regel wirken sich diese zusätzlichen Funktionen nicht auf Client Anwendungen aus, da der WCF-Client mehrere Aufrufe ausführt und dann beendet wird.  
  
 Client Anwendungen der mittleren Ebene können jedoch viele WCF-Client Objekte schnell erstellen und somit die Initialisierungs Anforderungen steigern. Für die Leistungsoptimierung von Anwendungen mittlerer Ebene beim Aufrufen von Diensten haben Sie die Wahl zwischen zwei grundsätzlichen Vorgehensweisen:  
  
- Zwischenspeichern des WCF-Client Objekts und Wiederverwendung für nachfolgende Aufrufe, sofern möglich.  
  
- Erstellen <xref:System.ServiceModel.ChannelFactory%601> Sie ein-Objekt, und verwenden Sie dieses Objekt dann, um für jeden-Befehl neue WCF-Client Kanal Objekte zu erstellen.  
  
 Bei diesen Vorgehensweisen sollten Sie Folgendes beachten:  
  
- Wenn der Dienst einen Client spezifischen Zustand mithilfe einer-Sitzung verwaltet, können Sie den WCF-Client der mittleren Ebene nicht mit Anforderungen auf der Ebene von mehreren Clients wieder verwenden, da der Dienststatus an den Client der mittleren Ebene gebunden ist.  
  
- Wenn der Dienst die Authentifizierung pro Client ausführen muss, müssen Sie für jede eingehende Anforderung auf der mittleren Ebene einen neuen Client erstellen, anstatt den WCF-Client der mittleren Ebene (oder das WCF-Client Kanal Objekt) wieder zu verwenden, da die Client Anmelde Informationen der mittleren Ebene nach der Erstellung des WCF-Clients (oder) nicht mehr geändert werden können <xref:System.ServiceModel.ChannelFactory%601> .  
  
- Channels und von den Channels erstellte Clients sind zwar threadsicher, unterstützen jedoch möglicherweise keine gleichzeitigen Schreibvorgänge mehrerer Nachrichten zur Übertragung. Beim Senden umfangreicher Nachrichten (und besonders beim Streaming) wird der Sendevorgang möglicherweise blockiert, da auf den Abschluss eines anderen Sendevorgangs gewartet wird. Daraus ergeben sich zwei Probleme: fehlende Parallelität und die Gefahr eines Deadlocks, wenn die Ablaufsteuerung wieder zu dem Dienst zurückkehrt, von dem der Channel wiederverwendet wird (oder mit anderen Worten: Wenn vom freigegebenen Client ein Dienst aufgerufen wird, dessen Codepfad einen Rückruf an den freigegebenen Client auslöst). Dies gilt unabhängig vom Typ des wiederzuverwendenden WCF-Clients.  
  
- Fehler in Channels müssen unabhängig davon behoben werden, ob der Channel freigegeben ist. Beim Wiederverwenden von Channels kann ein fehlerhafter Channel dazu führen, dass gleich mehrere ausstehende Anforderungen oder Sendevorgänge nicht ausgeführt werden.  
  
 Ein Beispiel, das bewährte Methoden für die Wiederverwendung eines Clients für mehrere Anforderungen veranschaulicht, finden Sie unter [Datenbindung in einem ASP.NET-Client](../samples/data-binding-in-an-aspnet-client.md).  
  
 Darüber hinaus können Sie die Leistung beim Starten von Clients verbessern, von denen serialisierbare Datentypen verwendet werden. Für die Serialisierung dieser Datentypen wird der Serialisierungscode von <xref:System.Xml.Serialization.XmlSerializer> zum Generieren und Kompilieren zur Laufzeit verwendet, was eine Beeinträchtigung der Leistung beim Start zur Folge haben kann. Das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) kann die Startleistung für diese Anwendungen verbessern, indem der erforderliche Serialisierungscode aus den kompilierten Assemblys für die Anwendung erzeugt wird. Weitere Informationen finden Sie unter Vorgehens [Weise: verbessern der Startzeit von WCF-Client Anwendungen mit dem XmlSerializer](startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Zugreifen auf Dienste mithilfe eines WCF-Clients](accessing-services-using-a-client.md)
