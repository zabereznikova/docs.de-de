---
title: "Datenübertragung und Serialisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29ca4041e24a99546dfb665b0ce9e695732442d4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="data-transfer-and-serialization"></a>Datenübertragung und Serialisierung
In einem verbundenen System müssen Dienste und Clients Daten austauschen, um Aufgaben auszuführen. Als Entwickler eines Diensts oder Clients müssen Sie zudem wissen, wie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mit Daten und der Datenserialisierung verfährt, um Anwendungen erstellen zu können, die effizient und einfach zu pflegen sind.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Specifying Data Transfer in Service Contracts](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 Beschreibt die grundlegenden Aspekte der Datenübertragung in Diensten.  
  
 [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 Beschreibt, was Datenverträge sind und wie sie erstellt und verwendet werden.  
  
 [Datenvertrags-Serialisierer](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 Beschreibt, wie die Datenserialisierung mit der <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse oder einer Erweiterung der <xref:System.Runtime.Serialization.XmlObjectSerializer>-Klasse durchgeführt wird.  
  
 [Verwenden der XmlSerializer-Klasse](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 Beschreibt, wie und warum die <xref:System.Xml.Serialization.XmlSerializer>-Klasse, eine Alternative zur <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse, verwendet wird.  
  
 [Verwendung von Nachrichtenverträgen](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 Beschreibt, wie Nachrichtenverträge die genaue Steuerung von SOAP-Nachrichten ermöglichen.  
  
 [Verwenden der Message-Klasse](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 Beschreibt, wie Nachrichtenklassenfunktionen verwendet werden.  
  
 [Filtern](../../../../docs/framework/wcf/feature-details/filtering.md)  
 Beschreibt die Filterung, die eine Vorverarbeitung von Nachrichten auf der Grundlage verschiedener Kriterien ermöglicht.  
  
 [Umfangreiche Daten und Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 Beschreibt, wie ein großer Datenblock gesendet wird, z.&#160;B. eine Binärdatei.  
  
 [Sicherheitsüberlegungen zu Daten](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 Beschreibt Dinge, auf die bei der Programmierung der Datenübertragung und Datenserialisierung geachtet werden müssen.  
  
 [Datenübertragungsarchitektur-Übersicht](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 Beschreibt einen Überblick über den Gesamtentwurf der Datenübertragung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="reference"></a>Verweis  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Erweitern von Encodern und Serialisierungsprogrammen](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Bewährte Methoden: Versionsverwaltung von Datenverträgen](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [Dienstversionsverwaltung](../../../../docs/framework/wcf/service-versioning.md)
