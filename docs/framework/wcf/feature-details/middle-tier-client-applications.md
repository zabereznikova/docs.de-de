---
title: Clientanwendungen mittlerer Ebene
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 893fa027d2f1eb4fa3782b9119f6ae2d4a78d700
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="middle-tier-client-applications"></a>Clientanwendungen mittlerer Ebene
In diesem Thema werden verschiedene Probleme bezüglich Clientanwendungen mittlerer Ebene diskutiert, von denen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet wird.  
  
## <a name="increasing-middle-tier-client-performance"></a>Verbessern der Leistung von Clients mittlerer Ebene  
 Im Vergleich zu früheren Kommunikationstechnologien wie Webdiensten unter Verwendung von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] kann das Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientinstanz aufgrund der umfangreichen Funktionen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] etwas komplexer ausfallen. Beispiel: Beim Öffnen eines <xref:System.ServiceModel.ChannelFactory%601>-Objekts kann von diesem Objekt eine sichere Sitzung mit dem Dienst hergestellt werden, was zu einer Verlängerung der Startzeit der Clientinstanz führt. Üblicherweise haben diese zusätzlichen Funktionen keine sonderlich großen Auswirkungen auf Clientanwendungen, da vom [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client lediglich einige Aufrufe ausgeführt werden und er anschließend geschlossen wird.  
  
 Von Clientanwendungen mittlerer Ebene kann jedoch in kurzer Zeit eine Vielzahl von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientobjekten erstellt werden. Daher besitzt dieser Typ höhere Initialisierungsanforderungen. Für die Leistungsoptimierung von Anwendungen mittlerer Ebene beim Aufrufen von Diensten haben Sie die Wahl zwischen zwei grundsätzlichen Vorgehensweisen:  
  
-   Zwischenspeichern des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientobjekts und anschließendes Wiederverwenden des Objekts für alle nachfolgenden Aufrufe (sofern möglich).  
  
-   Erstellen eines <xref:System.ServiceModel.ChannelFactory%601>-Objekts und anschließendes Verwenden des Objekts zum Erstellen eines neuen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientkanalobjekts für jeden Aufruf.  
  
 Bei diesen Vorgehensweisen sollten Sie Folgendes beachten:  
  
-   Wird vom Dienst ein clientspezifischer Zustand mithilfe einer Sitzung verwaltet, kann der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client mittlerer Ebene nicht mit mehrfachen Clientebenenanforderungen wiederverwendet werden, da der Zustand des Diensts direkt an den des Clients mittlerer Ebene gebunden ist.  
  
-   Muss der Dienst einzeln pro Client authentifiziert werden, ist das Erstellen eines neuen Clients für jede eingehende Anforderung mittlerer Ebene erforderlich. Das Wiederverwenden des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients mittlerer Ebene (oder des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientkanalobjekts) ist nicht möglicht, da die Anmeldeinformationen des Clients mittlerer Ebene nicht nach dem Erstellen des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients (oder nach dem Erstellen von <xref:System.ServiceModel.ChannelFactory%601>) geändert werden können.  
  
-   Channels und von den Channels erstellte Clients sind zwar threadsicher, unterstützen jedoch möglicherweise keine gleichzeitigen Schreibvorgänge mehrerer Nachrichten zur Übertragung. Beim Senden umfangreicher Nachrichten (und besonders beim Streaming) wird der Sendevorgang möglicherweise blockiert, da auf den Abschluss eines anderen Sendevorgangs gewartet wird. Daraus ergeben sich zwei Probleme: fehlende Parallelität und die Gefahr eines Deadlocks, wenn die Ablaufsteuerung wieder zu dem Dienst zurückkehrt, von dem der Channel wiederverwendet wird (oder mit anderen Worten: Wenn vom freigegebenen Client ein Dienst aufgerufen wird, dessen Codepfad einen Rückruf an den freigegebenen Client auslöst). Dies gilt unabhängig vom Typ des wiederverwendeten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients.  
  
-   Fehler in Channels müssen unabhängig davon behoben werden, ob der Channel freigegeben ist. Beim Wiederverwenden von Channels kann ein fehlerhafter Channel dazu führen, dass gleich mehrere ausstehende Anforderungen oder Sendevorgänge nicht ausgeführt werden.  
  
 Ein Beispiel für bewährte Methoden für die Wiederverwendung von einem Client mehrere Anforderungen finden Sie unter [Binden von Daten in einem ASP.NET-Client](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md).  
  
 Darüber hinaus können Sie die Leistung beim Starten von Clients verbessern, von denen serialisierbare Datentypen verwendet werden. Für die Serialisierung dieser Datentypen wird der Serialisierungscode von <xref:System.Xml.Serialization.XmlSerializer> zum Generieren und Kompilieren zur Laufzeit verwendet, was eine Beeinträchtigung der Leistung beim Start zur Folge haben kann. Die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) können startleistung für diese Anwendungen durch Generieren der erforderlichen Serialisierungscode aus den kompilierten Assemblys für die Anwendung zu verbessern. Weitere Informationen finden Sie unter [wie: Verbessern der Start Time des WCF-Clientanwendungen mit dem XmlSerializer](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zugreifen auf Dienste mithilfe eines WCF-Clients](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)
