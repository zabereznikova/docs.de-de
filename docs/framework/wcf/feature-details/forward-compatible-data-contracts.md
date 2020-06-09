---
title: Aufwärtskompatible Datenverträge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], forward compatibility
ms.assetid: 413c9044-26f8-4ecb-968c-18495ea52cd9
ms.openlocfilehash: 34bde56b78ec0148cf6b924f8edd29343b97faa4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597383"
---
# <a name="forward-compatible-data-contracts"></a>Aufwärtskompatible Datenverträge
Eine Funktion des Windows Communication Foundation (WCF)-Daten Vertragssystems ist, dass sich Verträge im Laufe der Zeit auf nicht unterbrechende Weise weiterentwickeln können. Dies bedeutet, dass ein Client mit einer älteren Version eines Datenvertrags mit einem Dienst, der eine neuere Version dieses Datenvertrags aufweist, kommunizieren kann bzw. dass ein Client mit einer neueren Version eines Datenvertrags mit einer älteren Version dieses Datenvertrags kommunizieren kann. Weitere Informationen finden Sie unter [bewährte Methoden: Versionsverwaltung von Daten Verträgen](../best-practices-data-contract-versioning.md).  
  
 Sie können beim Erstellen neuer Versionen eines bestehenden Datenvertrags die meisten Versionsverwaltungsfunktionen nach Bedarf verwenden. Allerdings muss eine Versionsverwaltung, *Roundtripping*, in den Typ der ersten Version integriert werden, damit Sie ordnungsgemäß funktioniert.  
  
## <a name="round-tripping"></a>Roundtrip-Funktion  
 Ein Roundtrip findet statt, wenn Daten von einer neuen Version an eine alte Version und wieder zurück an die neue Version eines Datenvertrags übergeben werden. Durch den Roundtrip wird sichergestellt, dass keine Daten verloren gehen. Durch die aktivierte Roundtrip-Funktion wird der Typ aufwärtskompatibel, das heißt, dass alle zukünftigen Änderungen vom Versionsverwaltungsmodell des Datenvertrags unterstützt werden.  
  
 Um die Roundtrip-Funktion für einen bestimmten Typ zu aktivieren, muss der Typ die <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle implementieren. Die Schnittstelle enthält die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>-Eigenschaft (und gibt den <xref:System.Runtime.Serialization.ExtensionDataObject>-Typ zurück). In der Eigenschaft werden alle Daten aus zukünftigen Versionen des Datenvertrags, die in der aktuellen Version unbekannt sind, gespeichert.  
  
### <a name="example"></a>Beispiel  
 Der folgende Datenvertrag ist nicht mit zukünftigen Änderungen aufwärtskompatibel:  
  
 [!code-csharp[C_DataContract#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#7)]
 [!code-vb[C_DataContract#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#7)]  
  
 Damit der Typ mit zukünftigen Änderungen (wie zum Beispiel einem hinzugefügten Datenmember "phoneNumber") kompatibel wird, muss die <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle implementiert werden.  
  
 [!code-csharp[C_DataContract#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#8)]
 [!code-vb[C_DataContract#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#8)]  
  
 Wenn in der WCF-Infrastrukturdaten gefunden werden, die nicht Teil des ursprünglichen Daten Vertrags sind, werden die Daten in der-Eigenschaft gespeichert und beibehalten. Eine Verarbeitung erfolgt nur für die vorübergehende Speicherung. Wird das Objekt an seinen Ursprungsort zurückgegeben, werden die ursprünglichen (unbekannten) Daten ebenfalls zurückgegeben. Auf diese Weise durchlaufen die Daten ohne Verlust einen Roundtrip zum und vom ursprünglichen Endpunkt. Beachten Sie jedoch, dass der Endpunkt die Änderungen selbst erkennen und umsetzen muss, falls der ursprüngliche Endpunkt eine Verarbeitung der Daten erfordert und diese Voraussetzung nicht erfüllt werden kann.  
  
 Der <xref:System.Runtime.Serialization.ExtensionDataObject>-Typ enthält keine öffentlichen Methoden oder Eigenschaften. Daher kann nicht direkt auf die in der <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>-Eigenschaft gespeicherten Daten zugegriffen werden.  
  
 Sie können die Roundtrip-Funktion deaktivieren. Legen Sie hierfür entweder `ignoreExtensionDataObject` im `true`-Konstruktor auf <xref:System.Runtime.Serialization.DataContractSerializer> fest, oder legen Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A>-Eigenschaft im `true` auf <xref:System.ServiceModel.ServiceBehaviorAttribute> fest. Wenn diese Funktion deaktiviert ist, wird die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>-Eigenschaft nicht vom Deserialisierungsprogramm gefüllt, und der Inhalt der Eigenschaft wird nicht vom Serialisierungsprogramm ausgegeben.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.IExtensibleDataObject>
- <xref:System.Runtime.Serialization.ExtensionDataObject>
- [Datenvertragsversionsverwaltung](data-contract-versioning.md)
- [Bewährte Methoden: Datenvertragsversionsverwaltung](../best-practices-data-contract-versioning.md)
