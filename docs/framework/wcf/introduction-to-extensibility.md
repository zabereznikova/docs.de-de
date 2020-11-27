---
title: Einführung in die Erweiterbarkeit
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], extensibility
- Windows Communication Foundation [WCF], extensibility
- extensibility [WCF]
ms.assetid: ef56c251-d63c-4b3f-944f-b0c67bfb0f68
ms.openlocfilehash: 8f4cc490df49a91e448c02fef370ce828536f907
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262722"
---
# <a name="introduction-to-extensibility"></a>Einführung in die Erweiterbarkeit

Das Anwendungsmodell Windows Communication Foundation (WCF) ist so konzipiert, dass der größere Teil der Kommunikationsanforderungen aller verteilten Anwendungen gelöst wird. Es treten jedoch häufig Szenarien auf, die das Standardanwendungsmodell und vom System bereitgestellte Implementierungen nicht unterstützen. Das WCF-Erweiterbarkeits Modell ist für die Unterstützung benutzerdefinierter Szenarien gedacht, da Sie das Systemverhalten auf jeder Ebene ändern können, sogar bis zum Ersetzen des gesamten Anwendungs Modells. Dieses Thema gliedert die verschiedenen Bereiche der Erweiterung und verweist auf weitere Informationen zu jeder Erweiterung.  
  
## <a name="areas-to-extend"></a>Zu erweiternde Bereiche  

 Folgende Werte können erweitert werden:  
  
- Die Anwendungslaufzeit. Dies erweitert das Zustellen und Verarbeiten von Nachrichten für die Anwendung. Dieser Bereich beinhaltet auch die Erweiterung von Sicherheitssystem, Metadatensystem, Serialisierungssystem und der Bindungen und Bindungselemente, die die Anwendung mit dem zugrunde liegenden Kanalsystem verbinden.  
  
- Der Kanal und die Kanallaufzeit. Dadurch wird das auf Nachrichtenebene funktionierende System erweitert und Protokoll-, Transport- und Codierungsunterstützung bereitgestellt.  
  
- Die Hostlaufzeit. Dadurch wird die Beziehung der Hostinganwendungsdomäne zum Kanal und der Anwendungslaufzeit erweitert.  
  
### <a name="extending-the-application-runtime"></a>Erweitern der Anwendungslaufzeit  

 In WCF-Anwendungen gibt es einen Unterschied zwischen Nachrichten, die für einen entsprechenden Kanal bestimmt sind, und Nachrichten, die für die Anwendung selbst bestimmt sind. Kanalnachrichten unterstützen einige kanalbezogene Funktionen, zum Beispiel das Einrichten einer sicheren Konversation oder einer zuverlässigen Sitzung. Diese Nachrichten sind nicht für die Anwendungslaufzeit verfügbar; sie werden vor Einbeziehung der Anwendungsebene verarbeitet.  
  
 Anwendungsnachrichten beinhalten Daten für einen Client- oder einen Dienstvorgang, der von Ihnen oder einem Kunden erstellt wurde. Diese Nachrichten sind je nach Anforderung für das Erweiterungssystem auf Anwendungsebene in Nachrichten- oder Objektform verfügbar.  
  
 Alle Nachrichten durchlaufen das Kanalsystem; nur Anwendungsnachrichten werden vom Kanalsystem an die Anwendung weitergegeben. Um neue Funktionen auf Kanalebene zu erstellen, muss das Kanalsystem erweitert werden. Sollen neue Funktionen auf Anwendungsebene erstellt werden, muss die Dienst- oder Clientlaufzeit (Verteiler bzw. Kanalfactorys) erweitert werden. Weitere Informationen zum Erweitern der Anwendungs Laufzeit finden Sie unter [Erweitern von Service Host und der Dienstmodell Ebene](./extending/extending-servicehost-and-the-service-model-layer.md).  
  
#### <a name="extending-security"></a>Erweitern der Sicherheit  

 Um benutzerdefinierte Sicherheitsmechanismen (zum Beispiel Token und Anmeldeinformationen) zu erstellen, muss das Sicherheitssystem erweitert werden. Weitere Informationen finden Sie unter [Erweitern der Sicherheit](./extending/extending-security.md).  
  
#### <a name="extending-metadata"></a>Erweitern von Metadaten  

 Sollen die Metadaten nicht nur im Standardsystem verfügbar gemacht werden, muss das Metadatensystem erweitert werden. Weitere Informationen finden Sie unter [Erweitern des Metadatensystems](./extending/extending-the-metadata-system.md).  
  
#### <a name="extending-serialization"></a>Erweitern der Serialisierung  

 Wenn Sie benutzerdefinierte Encoder erstellen und Datenersatzzeichen oder andere Elemente, bei denen übertragene Daten angepasst werden, bereitstellen möchten, erweitern Sie das Serialisierungssystem. Weitere Informationen finden Sie unter [Erweitern von Encodern und serialisierungsinitialisierern](./extending/extending-encoders-and-serializers.md).  
  
#### <a name="extending-bindings"></a>Erweitern von Bindungen  

 Sollen Transport- oder Protokollkanäle der Anwendungsebene zugeordnet werden, muss das Bindungssystem erweitert werden. Weitere Informationen finden Sie unter [Erweitern von Bindungen](./extending/extending-bindings.md).  
  
### <a name="extending-the-channel-system"></a>Erweitern des Kanalsystems  

 Informationen zum Erstellen von Kanälen, die benutzerdefinierte Transporte oder Protokollfunktionen unterstützen, finden Sie unter [Erweitern der Kanal Ebene](./extending/extending-the-channel-layer.md).  
  
### <a name="extending-the-service-hosting-system"></a>Erweitern des Diensthostsystems  

 Soll das dienstweite Anwendungsmodell geändert werden, ist eine Erweiterung der <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>-Klasse erforderlich. Weitere Informationen finden Sie unter [Erweitern von Service Host und der Dienstmodell Ebene](./extending/extending-servicehost-and-the-service-model-layer.md).  
  
 Soll die Beziehung zwischen der Hostanwendungsdomäne und dem Diensthost geändert werden, ist eine Erweiterung der <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType>-Klasse erforderlich. Weitere Informationen finden Sie unter [Erweitern des Hosting mit ServiceHostFactory](./extending/extending-hosting-using-servicehostfactory.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweitern von WCF](./extending/index.md)
