---
title: Datenübertragung und Serialisierung
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: b07937b0a94c24a934b17d6cf21b726ee0d4362e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593486"
---
# <a name="data-transfer-and-serialization"></a>Datenübertragung und Serialisierung
In einem verbundenen System müssen Dienste und Clients Daten austauschen, um Aufgaben auszuführen. Als Entwickler eines Diensts oder Clients müssen Sie auch verstehen, wie Windows Communication Foundation (WCF) die Daten-und Datenserialisierung behandelt, um Anwendungen zu erstellen, die effizient und einfach zu verwalten sind.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Angeben von Datenübertragung in Dienstverträgen](specifying-data-transfer-in-service-contracts.md)  
 Beschreibt die grundlegenden Aspekte der Datenübertragung in Diensten.  
  
 [Verwenden von Datenverträgen](using-data-contracts.md)  
 Beschreibt, was Datenverträge sind und wie sie erstellt und verwendet werden.  
  
 [Datenvertragsserialisierer](data-contract-serializer.md)  
 Beschreibt, wie die Datenserialisierung mit der <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse oder einer Erweiterung der <xref:System.Runtime.Serialization.XmlObjectSerializer>-Klasse durchgeführt wird.  
  
 [Verwenden der XmlSerializer-Klasse](using-the-xmlserializer-class.md)  
 Beschreibt, wie und warum die <xref:System.Xml.Serialization.XmlSerializer>-Klasse, eine Alternative zur <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse, verwendet wird.  
  
 [Verwendung von Nachrichtenverträgen](using-message-contracts.md)  
 Beschreibt, wie Nachrichtenverträge die genaue Steuerung von SOAP-Nachrichten ermöglichen.  
  
 [Verwenden der Message-Klasse](using-the-message-class.md)  
 Beschreibt, wie Nachrichtenklassenfunktionen verwendet werden.  
  
 [Filterung](filtering.md)  
 Beschreibt die Filterung, die eine Vorverarbeitung von Nachrichten auf der Grundlage verschiedener Kriterien ermöglicht.  
  
 [Umfangreiche Daten und Streaming](large-data-and-streaming.md)  
 Beschreibt, wie ein großer Datenblock gesendet wird, z.&#160;B. eine Binärdatei.  
  
 [Sicherheitsüberlegungen zu Daten](security-considerations-for-data.md)  
 Beschreibt Dinge, auf die bei der Programmierung der Datenübertragung und Datenserialisierung geachtet werden müssen.  
  
 [Datenübertragungsarchitektur - Übersicht](data-transfer-architectural-overview.md)  
 Beschreibt eine Ansicht des Gesamt Entwurfs der Datenübertragung in WCF.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Erweitern von Encodern und Serialisierungsprogrammen](../extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Bewährte Methoden: Datenvertragsversionsverwaltung](../best-practices-data-contract-versioning.md)
- [Dienst Versionsverwaltung](../service-versioning.md)
