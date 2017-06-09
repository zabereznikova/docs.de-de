---
title: "Einf&#252;hrung in die Erweiterbarkeit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Erweiterbarkeit [WCF]"
  - "WCF [WCF], Erweiterbarkeit"
  - "Windows Communication Foundation [WCF], Erweiterbarkeit"
ms.assetid: ef56c251-d63c-4b3f-944f-b0c67bfb0f68
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Einf&#252;hrung in die Erweiterbarkeit
Mit dem [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Anwendungsmodell wird den meisten Kommunikationsanforderungen aller beliebigen verteilten Anwendungen entsprochen.  Es treten jedoch häufig Szenarien auf, die das Standardanwendungsmodell und vom System bereitgestellte Implementierungen nicht unterstützen.  Mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Erweiterbarkeitsmodell werden benutzerdefinierte Szenarien unterstützt, indem das Systemverhalten auf jeder Ebene geändert werden kann. Dies ist sogar bis zum Ersatz des gesamten Anwendungsmodells möglich.  Dieses Thema gliedert die verschiedenen Bereiche der Erweiterung und verweist auf weitere Informationen zu jeder Erweiterung.  
  
## Zu erweiternde Bereiche  
 Folgende Werte können erweitert werden:  
  
-   Die Anwendungslaufzeit.  Dies erweitert das Zustellen und Verarbeiten von Nachrichten für die Anwendung.  Dieser Bereich beinhaltet auch die Erweiterung von Sicherheitssystem, Metadatensystem, Serialisierungssystem und der Bindungen und Bindungselemente, die die Anwendung mit dem zugrunde liegenden Kanalsystem verbinden.  
  
-   Der Kanal und die Kanallaufzeit.  Dadurch wird das auf Nachrichtenebene funktionierende System erweitert und Protokoll\-, Transport\- und Codierungsunterstützung bereitgestellt.  
  
-   Die Hostlaufzeit.  Dadurch wird die Beziehung der Hostinganwendungsdomäne zum Kanal und der Anwendungslaufzeit erweitert.  
  
### Erweitern der Anwendungslaufzeit  
 In [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Anwendungen unterscheidet man zwischen Nachrichten, die für einen entsprechenden Kanal und Nachrichten, die für die Anwendung selbst vorgesehen sind.  Kanalnachrichten unterstützen einige kanalbezogene Funktionen, zum Beispiel das Einrichten einer sicheren Konversation oder einer zuverlässigen Sitzung.  Diese Nachrichten sind nicht für die Anwendungslaufzeit verfügbar; sie werden vor Einbeziehung der Anwendungsebene verarbeitet.  
  
 Anwendungsnachrichten beinhalten Daten für einen Client\- oder einen Dienstvorgang, der von Ihnen oder einem Kunden erstellt wurde.  Diese Nachrichten sind je nach Anforderung für das Erweiterungssystem auf Anwendungsebene in Nachrichten\- oder Objektform verfügbar.  
  
 Alle Nachrichten durchlaufen das Kanalsystem; nur Anwendungsnachrichten werden vom Kanalsystem an die Anwendung weitergegeben.  Um neue Funktionen auf Kanalebene zu erstellen, muss das Kanalsystem erweitert werden.  Sollen neue Funktionen auf Anwendungsebene erstellt werden, muss die Dienst\- oder Clientlaufzeit \(Verteiler bzw. Kanalfactorys\) erweitert werden.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Erweitern der Anwendungslaufzeit finden Sie unter [Erweitern von ServiceHost und der Dienstmodellebene](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md).  
  
#### Erweitern der Sicherheit  
 Um benutzerdefinierte Sicherheitsmechanismen \(zum Beispiel Token und Anmeldeinformationen\) zu erstellen, muss das Sicherheitssystem erweitert werden.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Erweitern der Sicherheit](../../../docs/framework/wcf/extending/extending-security.md).  
  
#### Erweitern von Metadaten  
 Sollen die Metadaten nicht nur im Standardsystem verfügbar gemacht werden, muss das Metadatensystem erweitert werden.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Erweitern des Metadatensystems](../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
#### Erweitern der Serialisierung  
 Wenn Sie benutzerdefinierte Encoder erstellen und Datenersatzzeichen oder andere Elemente, bei denen übertragene Daten angepasst werden, bereitstellen möchten, erweitern Sie das Serialisierungssystem.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Erweitern von Encodern und Serialisierungsprogrammen](../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md).  
  
#### Erweitern von Bindungen  
 Sollen Transport\- oder Protokollkanäle der Anwendungsebene zugeordnet werden, muss das Bindungssystem erweitert werden.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Erweitern von Bindungen](../../../docs/framework/wcf/extending/extending-bindings.md).  
  
### Erweitern des Kanalsystems  
 Informationen zum Erstellen von Kanälen, die benutzerdefinierte Transporte oder Protokollfunktionen unterstützen, erhalten Sie unter [Erweitern der Kanalschicht](../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
### Erweitern des Diensthostsystems  
 Soll das dienstweite Anwendungsmodell geändert werden, ist eine Erweiterung der <xref:System.ServiceModel.ServiceHostBase?displayProperty=fullName>\-Klasse erforderlich.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Erweitern von ServiceHost und der Dienstmodellebene](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md).  
  
 Soll die Beziehung zwischen der Hostanwendungsdomäne und dem Diensthost geändert werden, ist eine Erweiterung der <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=fullName>\-Klasse erforderlich.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Erweitern des Hosting mit ServiceHostFactory](../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md).  
  
## Siehe auch  
 [Erweitern von WCF](../../../docs/framework/wcf/extending/extending-wcf.md)