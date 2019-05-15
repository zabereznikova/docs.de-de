---
title: Verwenden von Datenverträgen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataContractAttribute class
- WCF, data
- data contracts [WCF]
ms.assetid: a3ae7b21-c15c-4c05-abd8-f483bcbf31af
ms.openlocfilehash: 3fd22cc0842c51b331905369915bd055235680c4
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592188"
---
# <a name="using-data-contracts"></a>Verwenden von Datenverträgen
Ein neuer *Datenvertrag* ist eine formale Vereinbarung zwischen einem Dienst und einem Client, in dem die auszutauschenden Daten abstrakt beschrieben werden. Das heißt, der Client und der Dienst müssen, um kommunizieren zu können, nicht denselben Typ verwenden, sondern nur dieselben Datenverträge. Ein Datenvertrag definiert für jeden Parameter oder Rückgabetyp genau, welche Daten für einen Austausch serialisiert (in XML umgewandelt) werden.  
  
## <a name="data-contract-basics"></a>Grundlagen des Datenvertrags  
 Windows Communication Foundation (WCF) verwendet eine Serialisierungs-Engine standardmäßig den Namen der Data Contract Serializer serialisiert und deserialisiert Daten (Umwandeln in und aus XML-Code). Alle .NET Framework-primitive Typen wie Ganzzahlen und Zeichenfolgen, als auch für bestimmte Typen, die als Primitiv behandelt werden, z. B. <xref:System.DateTime> und <xref:System.Xml.XmlElement>, ohne weitere Vorbereitung serialisiert werden kann, und gelten als Standard-Datenverträge müssen. Viele .NET Framework-Typen haben jedoch auch vorhandene Datenverträge. Eine vollständige Liste der serialisierbaren Typen finden Sie unter [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).  
  
 Für neue komplexe Typen, die Sie erstellen, muss ein Datenvertrag definiert sein, damit sie serialisierbar sind. Standardmäßig leitet der <xref:System.Runtime.Serialization.DataContractSerializer> den Datenvertrag ab und serialisiert alle öffentlich sichtbaren Typen. Alle öffentlichen Lese-/Schreibeigenschaften und Felder des Typs werden serialisiert. Mithilfe des <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>können Member von der Serialisierung ausgeschlossen werden. Mit dem <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut und dem <xref:System.Runtime.Serialization.DataMemberAttribute> -Attribut können Sie auch explizit einen Datenvertrag erstellen. Wenden Sie dazu das <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut auf den Typ an. Dieses Attribut kann auf Klassen, Strukturen und Enumerationen angewendet werden. Das <xref:System.Runtime.Serialization.DataMemberAttribute> -Attribut muss dann auf jeden Member des Datenvertragstyps angewendet werden, um anzugeben, dass es sich um einen *Datenmember*handelt, d.&#160;h., dass er serialisiert werden soll. Weitere Informationen finden Sie unter [serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Dienstvertrag (eine Schnittstelle) dargestellt, auf die die Attribute <xref:System.ServiceModel.ServiceContractAttribute> und <xref:System.ServiceModel.OperationContractAttribute> explizit angewendet wurden. Das Beispiel zeigt, dass primitive Typen keinen Datenvertrag erfordern, ein komplexer Typ jedoch schon.  
  
 [!code-csharp[C_DataContract#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#1)]
 [!code-vb[C_DataContract#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#1)]  
  
 Das folgende Beispiel veranschaulicht, wie Sie einen Datenvertrag für den `MyTypes.PurchaseOrder` -Typ erstellen, indem Sie die Attribute <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Klassen und ihre Member anwenden.  
  
 [!code-csharp[C_DataContract#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#2)]
 [!code-vb[C_DataContract#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#2)]  
  
### <a name="notes"></a>Hinweise  
 Berücksichtigen Sie beim Erstellen von Datenverträgen die folgenden Hinweise:  
  
- Das <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> -Attribut wird nur berücksichtigt, wenn es zusammen mit nicht markierten Typen verwendet wird. Dazu zählen Typen, die weder mit einem <xref:System.Runtime.Serialization.DataContractAttribute>-, <xref:System.SerializableAttribute>-, <xref:System.Runtime.Serialization.CollectionDataContractAttribute>- oder <xref:System.Runtime.Serialization.EnumMemberAttribute> -Attribut noch auf andere Weise als serialisierbar markiert sind (beispielsweise mithilfe von <xref:System.Xml.Serialization.IXmlSerializable>).  
  
- Sie können das <xref:System.Runtime.Serialization.DataMemberAttribute> -Attribut auf Felder und Eigenschaften anwenden.  
  
- Memberzugriffsebenen (internal, private, protected oder public) haben keinerlei Einfluss auf den Datenvertrag.  
  
- Das <xref:System.Runtime.Serialization.DataMemberAttribute> -Attribut wird ignoriert, wenn es auf statische Member angewendet wird.  
  
- Bei der Serialisierung werden mit einem Aufruf von property-get-Code für Eigenschaftsdatenmember die Werte der zu serialisierenden Eigenschaften abgerufen.  
  
- Bei der Deserialisierung wird zuerst ein nicht initialisiertes Objekt erstellt, ohne dass Konstruktoren für den Typ aufgerufen werden. Dann werden alle Datenmember deserialisiert.  
  
- Mit einem Aufruf von property-set-Code für Eigenschaftsdatenmember werden bei der Deserialisierung die Werte der zu deserialisierenden Eigenschaften festgelegt.  
  
- Damit ein Datenvertrag gültig ist, müssen alle seine Datenmember serialisiert werden können. Eine vollständige Liste der serialisierbaren Typen finden Sie unter [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).  
  
     Generische Typen werden auf genau die gleiche Weise behandelt wie nicht generische Typen. Es gibt keine besonderen Anforderungen für generische Parameter. Betrachten Sie z.&#160;B. den folgenden Typ:  
  
 [!code-csharp[C_DataContract#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#3)]
 [!code-vb[C_DataContract#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#3)]  
  
 Dieser Typ ist serialisierbar, unabhängig davon, ob der für den generischen Typparameter (`T`) verwendete Typ serialisierbar ist. Da das Serialisieren aller Datenmember möglich sein muss, ist der folgende Typ nur dann serialisierbar, wenn der generische Typparameter ebenfalls serialisierbar ist (wie im folgenden Code dargestellt):  
  
 [!code-csharp[C_DataContract#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#4)]
 [!code-vb[C_DataContract#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#4)]  
  
 Ein vollständiges Codebeispiel eines WCF-Diensts, der einen Datenvertrag definiert, finden Sie unter [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) .  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- [Serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md)
- [Datenvertragsnamen](../../../../docs/framework/wcf/feature-details/data-contract-names.md)
- [Datenvertragsäquivalenz](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)
- [Datenmemberreihenfolge](../../../../docs/framework/wcf/feature-details/data-member-order.md)
- [Bekannte Typen in Datenverträgen](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [Aufwärtskompatible Datenverträge](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)
- [Datenvertrags-Versionsverwaltung](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)
- [Versionstolerante Serialisierungsrückrufe](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md)
- [Standardwerte der Datenelemente](../../../../docs/framework/wcf/feature-details/data-member-default-values.md)
- [Vom Datenvertragsserialisierer unterstützte Typen](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
- [Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
