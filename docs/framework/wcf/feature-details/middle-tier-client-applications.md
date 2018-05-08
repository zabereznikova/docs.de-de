---
title: Clientanwendungen mittlerer Ebene
ms.date: 03/30/2017
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
ms.openlocfilehash: 4cca832266b2eb2ab7b1b4eb1a5fe937525db97d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="middle-tier-client-applications"></a>Clientanwendungen mittlerer Ebene
In diesem Artikel werden verschiedene Probleme bezüglich Clientanwendungen mittlerer Ebene, die Windows Communication Foundation (WCF) verwenden.  
  
## <a name="increasing-middle-tier-client-performance"></a>Verbessern der Leistung von Clients mittlerer Ebene  
 Im Vergleich zu früheren Kommunikationstechnologien wie Webdiensten unter Verwendung [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], die Erstellung einer Instanz der WCF-Client kann eine komplexere aufgrund der umfangreichen Funktionen von WCF. Beispiel: Beim Öffnen eines <xref:System.ServiceModel.ChannelFactory%601>-Objekts kann von diesem Objekt eine sichere Sitzung mit dem Dienst hergestellt werden, was zu einer Verlängerung der Startzeit der Clientinstanz führt. In der Regel wird wirken diese zusätzlichen Funktionen Clientanwendungen erheblich sich nicht, da die WCF-Client einige Aufrufe lediglich und dann schließt.  
  
 Clientanwendungen mittlerer Ebene, jedoch können viele WCF-Clientobjekten schnell und erstellen daher treten höhere initialisierungsanforderungen. Für die Leistungsoptimierung von Anwendungen mittlerer Ebene beim Aufrufen von Diensten haben Sie die Wahl zwischen zwei grundsätzlichen Vorgehensweisen:  
  
-   Zwischenspeichern Sie des WCF-Clientobjekts und für nachfolgende Aufrufe wiederverwenden Sie, sofern möglich.  
  
-   Erstellen einer <xref:System.ServiceModel.ChannelFactory%601> Objekt, und verwenden Sie dieses Objekt zum Erstellen von neuen WCF-Clients kanalobjekten, bei jedem Aufruf.  
  
 Bei diesen Vorgehensweisen sollten Sie Folgendes beachten:  
  
-   Wenn der Dienst einen clientspezifischer Zustand mithilfe einer Sitzungs verwaltet, können nicht Sie die WCF-Clients mittlerer Ebene mit mehreren-Clientebene Anforderungen wiederverwenden, da der Zustand des Diensts an, die von den Clients mittlerer Ebene gebunden ist.  
  
-   Wenn der Dienst auf einer pro-Client-Basis die Authentifizierung durchführen muss, müssen Sie einen neuen Client für jede eingehende Anforderung erstellen, auf der mittleren Ebene anstelle der WCF-Clients mittlerer Ebene (oder WCF-clientkanalobjekts) wiederverwenden, da die Anmeldeinformationen des Clients mittlerer Ebene kann nicht geändert werden, nachdem der WCF-Client (oder <xref:System.ServiceModel.ChannelFactory%601>) erstellt wurde.  
  
-   Channels und von den Channels erstellte Clients sind zwar threadsicher, unterstützen jedoch möglicherweise keine gleichzeitigen Schreibvorgänge mehrerer Nachrichten zur Übertragung. Beim Senden umfangreicher Nachrichten (und besonders beim Streaming) wird der Sendevorgang möglicherweise blockiert, da auf den Abschluss eines anderen Sendevorgangs gewartet wird. Daraus ergeben sich zwei Probleme: fehlende Parallelität und die Gefahr eines Deadlocks, wenn die Ablaufsteuerung wieder zu dem Dienst zurückkehrt, von dem der Channel wiederverwendet wird (oder mit anderen Worten: Wenn vom freigegebenen Client ein Dienst aufgerufen wird, dessen Codepfad einen Rückruf an den freigegebenen Client auslöst). Dies gilt unabhängig vom Typ des WCF-Clients, die Sie wiederverwenden.  
  
-   Fehler in Channels müssen unabhängig davon behoben werden, ob der Channel freigegeben ist. Beim Wiederverwenden von Channels kann ein fehlerhafter Channel dazu führen, dass gleich mehrere ausstehende Anforderungen oder Sendevorgänge nicht ausgeführt werden.  
  
 Ein Beispiel für bewährte Methoden für die Wiederverwendung von einem Client mehrere Anforderungen finden Sie unter [Binden von Daten in einem ASP.NET-Client](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md).  
  
 Darüber hinaus können Sie die Leistung beim Starten von Clients verbessern, von denen serialisierbare Datentypen verwendet werden. Für die Serialisierung dieser Datentypen wird der Serialisierungscode von <xref:System.Xml.Serialization.XmlSerializer> zum Generieren und Kompilieren zur Laufzeit verwendet, was eine Beeinträchtigung der Leistung beim Start zur Folge haben kann. Die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) können startleistung für diese Anwendungen durch Generieren der erforderlichen Serialisierungscode aus den kompilierten Assemblys für die Anwendung zu verbessern. Weitere Informationen finden Sie unter [wie: Verbessern der Start Time des WCF-Clientanwendungen mit dem XmlSerializer](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zugreifen auf Dienste mithilfe eines WCF-Clients](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)
