---
title: Aufwärtskompatible Datenverträge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], forward compatibility
ms.assetid: 413c9044-26f8-4ecb-968c-18495ea52cd9
ms.openlocfilehash: 90d9409d7e41ddda99caf24ebe0e249ee04723d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855906"
---
# <a name="forward-compatible-data-contracts"></a>Aufwärtskompatible Datenverträge
Eine Funktion von der Windows Communication Foundation (WCF) ist, die Verträge kann im Laufe der Zeit auf geschützte Weise entwickelt werden. Dies bedeutet, dass ein Client mit einer älteren Version eines Datenvertrags mit einem Dienst, der eine neuere Version dieses Datenvertrags aufweist, kommunizieren kann bzw. dass ein Client mit einer neueren Version eines Datenvertrags mit einer älteren Version dieses Datenvertrags kommunizieren kann. Weitere Informationen finden Sie unter [Best Practices: Versionsverwaltung von Datenverträgen](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).  
  
 Sie können beim Erstellen neuer Versionen eines bestehenden Datenvertrags die meisten Versionsverwaltungsfunktionen nach Bedarf verwenden. Allerdings eine Versionsverwaltungsfunktion, *Round-Tripping*, muss in den Typ der ersten Version erstellt werden, damit Sie einwandfrei funktionieren.  
  
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
  
 Wenn die WCF-Infrastruktur Daten, die nicht Teil des ursprünglichen Datenvertrag ist trifft, die Daten in der Eigenschaft gespeichert und beibehalten. Eine Verarbeitung erfolgt nur für die vorübergehende Speicherung. Wird das Objekt an seinen Ursprungsort zurückgegeben, werden die ursprünglichen (unbekannten) Daten ebenfalls zurückgegeben. Auf diese Weise durchlaufen die Daten ohne Verlust einen Roundtrip zum und vom ursprünglichen Endpunkt. Beachten Sie jedoch, dass der Endpunkt die Änderungen selbst erkennen und umsetzen muss, falls der ursprüngliche Endpunkt eine Verarbeitung der Daten erfordert und diese Voraussetzung nicht erfüllt werden kann.  
  
 Der <xref:System.Runtime.Serialization.ExtensionDataObject>-Typ enthält keine öffentlichen Methoden oder Eigenschaften. Daher kann nicht direkt auf die in der <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>-Eigenschaft gespeicherten Daten zugegriffen werden.  
  
 Sie können die Roundtrip-Funktion deaktivieren. Legen Sie hierfür entweder `ignoreExtensionDataObject` im `true`-Konstruktor auf <xref:System.Runtime.Serialization.DataContractSerializer> fest, oder legen Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A>-Eigenschaft im `true` auf <xref:System.ServiceModel.ServiceBehaviorAttribute> fest. Wenn diese Funktion deaktiviert ist, wird die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>-Eigenschaft nicht vom Deserialisierungsprogramm gefüllt, und der Inhalt der Eigenschaft wird nicht vom Serialisierungsprogramm ausgegeben.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.IExtensibleDataObject>
- <xref:System.Runtime.Serialization.ExtensionDataObject>
- [Datenvertrags-Versionsverwaltung](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)
- [Bewährte Methoden: Versionsverwaltung von Datenverträgen](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
