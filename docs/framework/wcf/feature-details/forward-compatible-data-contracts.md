---
title: "Aufwärtskompatible Datenverträge"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: data contracts [WCF], forward compatibility
ms.assetid: 413c9044-26f8-4ecb-968c-18495ea52cd9
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5ffd4a09de508a2353af356863f9e4f41fc253e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="forward-compatible-data-contracts"></a>Aufwärtskompatible Datenverträge
Ein Merkmal des [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Datenvertragssystems ist, dass sich Verträge im Laufe der Zeit ohne Unterbrechung weiterentwickeln können. Dies bedeutet, dass ein Client mit einer älteren Version eines Datenvertrags mit einem Dienst, der eine neuere Version dieses Datenvertrags aufweist, kommunizieren kann bzw. dass ein Client mit einer neueren Version eines Datenvertrags mit einer älteren Version dieses Datenvertrags kommunizieren kann. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweisen: Versionsverwaltung von Datenverträgen](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).  
  
 Sie können beim Erstellen neuer Versionen eines bestehenden Datenvertrags die meisten Versionsverwaltungsfunktionen nach Bedarf verwenden. Allerdings eine Versionsverwaltungsfunktion, *Round-Tripping*, muss in den Typ der ersten Version erstellt werden, damit Sie richtig funktioniert.  
  
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
  
 Wenn die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Infrastruktur auf Daten trifft, die nicht zum ursprünglichen Datenvertrag gehören, werden die Daten in der Eigenschaft gespeichert und so aufbewahrt. Eine Verarbeitung erfolgt nur für die vorübergehende Speicherung. Wird das Objekt an seinen Ursprungsort zurückgegeben, werden die ursprünglichen (unbekannten) Daten ebenfalls zurückgegeben. Auf diese Weise durchlaufen die Daten ohne Verlust einen Roundtrip zum und vom ursprünglichen Endpunkt. Beachten Sie jedoch, dass der Endpunkt die Änderungen selbst erkennen und umsetzen muss, falls der ursprüngliche Endpunkt eine Verarbeitung der Daten erfordert und diese Voraussetzung nicht erfüllt werden kann.  
  
 Der <xref:System.Runtime.Serialization.ExtensionDataObject>-Typ enthält keine öffentlichen Methoden oder Eigenschaften. Daher kann nicht direkt auf die in der <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>-Eigenschaft gespeicherten Daten zugegriffen werden.  
  
 Sie können die Roundtrip-Funktion deaktivieren. Legen Sie hierfür entweder `ignoreExtensionDataObject` im `true`-Konstruktor auf <xref:System.Runtime.Serialization.DataContractSerializer> fest, oder legen Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A>-Eigenschaft im `true` auf <xref:System.ServiceModel.ServiceBehaviorAttribute> fest. Wenn diese Funktion deaktiviert ist, wird die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>-Eigenschaft nicht vom Deserialisierungsprogramm gefüllt, und der Inhalt der Eigenschaft wird nicht vom Serialisierungsprogramm ausgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>  
 <xref:System.Runtime.Serialization.ExtensionDataObject>  
 [Datenvertrags-Versionsverwaltung](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)  
 [Bewährte Methoden: Versionsverwaltung von Datenverträgen](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
