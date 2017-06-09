---
title: "Aufw&#228;rtskompatible Datenvertr&#228;ge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Datenverträge [WCF], Aufwärtskompatibilität"
ms.assetid: 413c9044-26f8-4ecb-968c-18495ea52cd9
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Aufw&#228;rtskompatible Datenvertr&#228;ge
Ein Merkmal des [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Datenvertragssystems ist, dass sich Verträge im Laufe der Zeit ohne Unterbrechung weiterentwickeln können.Dies bedeutet, dass ein Client mit einer älteren Version eines Datenvertrags mit einem Dienst, der eine neuere Version dieses Datenvertrags aufweist, kommunizieren kann bzw. dass ein Client mit einer neueren Version eines Datenvertrags mit einer älteren Version dieses Datenvertrags kommunizieren kann.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Empfohlene Vorgehensweisen: Versionsverwaltung von Datenverträgen](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).  
  
 Sie können beim Erstellen neuer Versionen eines bestehenden Datenvertrags die meisten Versionsverwaltungsfunktionen nach Bedarf verwenden.Eine Versionsverwaltungsfunktion, der *Roundtrip*, muss jedoch von Anfang an in den Typ integriert werden, damit sie richtig funktioniert.  
  
## Roundtrip\-Funktion  
 Ein Roundtrip findet statt, wenn Daten von einer neuen Version an eine alte Version und wieder zurück an die neue Version eines Datenvertrags übergeben werden.Durch den Roundtrip wird sichergestellt, dass keine Daten verloren gehen.Durch die aktivierte Roundtrip\-Funktion wird der Typ aufwärtskompatibel, das heißt, dass alle zukünftigen Änderungen vom Versionsverwaltungsmodell des Datenvertrags unterstützt werden.  
  
 Um die Roundtrip\-Funktion für einen bestimmten Typ zu aktivieren, muss der Typ die <xref:System.Runtime.Serialization.IExtensibleDataObject>\-Schnittstelle implementieren.Die Schnittstelle enthält die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>\-Eigenschaft \(und gibt den <xref:System.Runtime.Serialization.ExtensionDataObject>\-Typ zurück\).In der Eigenschaft werden alle Daten aus zukünftigen Versionen des Datenvertrags, die in der aktuellen Version unbekannt sind, gespeichert.  
  
### Beispiel  
 Der folgende Datenvertrag ist nicht mit zukünftigen Änderungen aufwärtskompatibel:  
  
 [!code-csharp[C_DataContract#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#7)]
 [!code-vb[C_DataContract#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#7)]  
  
 Damit der Typ mit zukünftigen Änderungen \(wie zum Beispiel einem hinzugefügten Datenmember "phoneNumber"\) kompatibel wird, muss die <xref:System.Runtime.Serialization.IExtensibleDataObject>\-Schnittstelle implementiert werden.  
  
 [!code-csharp[C_DataContract#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#8)]
 [!code-vb[C_DataContract#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#8)]  
  
 Wenn die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Infrastruktur auf Daten trifft, die nicht zum ursprünglichen Datenvertrag gehören, werden die Daten in der Eigenschaft gespeichert und so aufbewahrt.Eine Verarbeitung erfolgt nur für die vorübergehende Speicherung.Wird das Objekt an seinen Ursprungsort zurückgegeben, werden die ursprünglichen \(unbekannten\) Daten ebenfalls zurückgegeben.Auf diese Weise durchlaufen die Daten ohne Verlust einen Roundtrip zum und vom ursprünglichen Endpunkt.Beachten Sie jedoch, dass der Endpunkt die Änderungen selbst erkennen und umsetzen muss, falls der ursprüngliche Endpunkt eine Verarbeitung der Daten erfordert und diese Voraussetzung nicht erfüllt werden kann.  
  
 Der <xref:System.Runtime.Serialization.ExtensionDataObject>\-Typ enthält keine öffentlichen Methoden oder Eigenschaften.Daher kann nicht direkt auf die in der <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>\-Eigenschaft gespeicherten Daten zugegriffen werden.  
  
 Sie können die Roundtrip\-Funktion deaktivieren. Legen Sie hierfür entweder `ignoreExtensionDataObject` im <xref:System.Runtime.Serialization.DataContractSerializer>\-Konstruktor auf `true` fest, oder legen Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A>\-Eigenschaft im <xref:System.ServiceModel.ServiceBehaviorAttribute> auf `true` fest.Wenn diese Funktion deaktiviert ist, wird die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>\-Eigenschaft nicht vom Deserialisierungsprogramm gefüllt, und der Inhalt der Eigenschaft wird nicht vom Serialisierungsprogramm ausgegeben.  
  
## Siehe auch  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>   
 <xref:System.Runtime.Serialization.ExtensionDataObject>   
 [Datenvertragsversionsverwaltung](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)   
 [Empfohlene Vorgehensweisen: Versionsverwaltung von Datenverträgen](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)