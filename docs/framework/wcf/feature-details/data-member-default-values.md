---
title: Standardwerte der Datenelemente
description: Erfahren Sie, wie Sie einen Datenmember aus serialisierten Daten weglassen, wenn dieser über einen .NET Framework Standardwert verfügt. WCF kann die Leistung verbessern, indem ein Standardwert nicht serialisiert wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data members [WCF], default values
- data members [WCF]
ms.assetid: 53a3b505-4b27-444b-b079-0eb84a97cfd8
ms.openlocfilehash: 97946a6b7da14efdcb5229b4cc5d0799eb8d7723
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247376"
---
# <a name="data-member-default-values"></a>Standardwerte der Datenelemente
In der .NET Framework verfügen Typen über ein Konzept von *Standardwerten*. Für jeden Referenztyp ist der Standardwert beispielsweise  `null`, und für einen Integertyp ist er 0 (null). Von Zeit zu Zeit ist es empfehlenswert, ein Datenelement aus serialisierten Daten zu entfernen, wenn es auf seinen Standardwert festgelegt ist. Da das Element seinen Standardwert besitzt, braucht kein tatsächlicher Wert serialisiert werden; dies führt zu einem Leistungsvorteil.  
  
 Um ein Element aus den serialisierten Daten zu löschen, legen Sie die Eigenschaft <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> des Attributs <xref:System.Runtime.Serialization.DataMemberAttribute> auf `false` fest (der Standardwert ist `true`).  
  
> [!NOTE]
> Sie sollten die <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>-Eigenschaft bei Bedarf auf `false` festlegen, z. B. aus Interoperabilitätsgründen oder zum Verringern der Datengröße.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code verfügt über mehrere Elemente, deren <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> auf `false` festgelegt ist.  
  
 [!code-csharp[DataMemberAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/datamemberattribute/cs/overview.cs#4)]
 [!code-vb[DataMemberAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datamemberattribute/vb/overview.vb#4)]  
  
 Wenn eine Instanz dieser Klasse serialisiert wird, ergibt sich folgendes Ergebnis: `employeeName` und `employeeID` sind serialisiert. Der Nullwert für `employeeName` und der Nullwert für `employeeID` sind ausdrücklich Teil der serialisierten Daten. Die Elemente `position`, `salary` und `bonus` sind hingegen nicht serialisiert. `targetSalary` wird wie gewöhnlich serialisiert, auch wenn die <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>-Eigenschaft auf `false` festgelegt ist, da "57800" nicht mit dem .NET-Standardwert einer ganzen Zahl ("0") übereinstimmt.  
  
### <a name="xml-representation"></a>XML-Darstellung  
 Wenn das vorherige Beispiel nach XML serialisiert wird, ähnelt die Darstellung Folgendem:  
  
```xml  
<Employee>  
   <employeeName xsi:nil="true" />  
   <employeeID>0</employeeID>  
<targetSalary>57800</targetSalary>  
</Employee>  
```  
  
 Das Attribut `xsi:nil` ist ein Spezialattribut im XML-Schemainstanz-Namespace des World Wide Web Consortium (W3C), der eine interoperable Möglichkeit bietet, speziell einen Nullwert darzustellen. Bitte beachten Sie, dass es im XML keinerlei Informationen über die Datenelemente Position, Gehalt und Bonus gibt. Die Emfangsseite kann diese als `null`, Null bzw. `null` interpretieren. Es gibt keine Garantie, dass einem Fremdanbieterdeserialisierer eine korrekte Auslegung gelingt; daher wird dieses Muster nicht empfohlen. Die Klasse <xref:System.Runtime.Serialization.DataContractSerializer> wählt immer die richtige Auslegung für fehlende Werte.  
  
### <a name="interaction-with-isrequired"></a>Interaktion mit IsRequired  
 Wie unter [Daten Vertrags Versions](data-contract-versioning.md)Verwaltung erläutert, weist das- <xref:System.Runtime.Serialization.DataMemberAttribute> Attribut eine- <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> Eigenschaft auf (die Standardeinstellung ist `false` ). Die Eigenschaft gibt an, ob ein bestimmtes Datenelement in den serialisierten Daten vorliegen muss, wenn sie deserialisiert werden. Wenn `IsRequired` auf `true` (gibt an, dass ein Wert vorliegen muss) und <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> auf `false` festgelegt ist (gibt an, dass der Wert nicht vorliegen muss, wenn das Element auf den Standardwert festgelegt ist), können Standardwerte für dieses Datenelement nicht serialisiert werden, da die Ergebnisse widersprüchlich wären. Wenn ein derartiges Datenelement auf seinen Standardwert gesetzt ist (normalerweise `null` oder 0 (null)) und eine Serialisierung versucht wird, wird eine <xref:System.Runtime.Serialization.SerializationException> ausgelöst.  
  
### <a name="schema-representation"></a>Schemendarstellung  
 Die Details der Schema Darstellung der XML-Schema Definitions Sprache (XSD) von Datenmembern, wenn die- `EmitDefaultValue` Eigenschaft auf festgelegt ist, `false` werden unter [Daten Vertrags Schema-Referenz](data-contract-schema-reference.md)erläutert. Im Folgenden wird jedoch nur eine kurze Übersicht gegeben:  
  
- Wenn <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> auf festgelegt ist `false` , wird es im Schema als Anmerkung dargestellt, die für Windows Communication Foundation (WCF) spezifisch ist. Es gibt keine interoperable Möglichkeit, diese Informationen darzustellen. Besonders das Attribut "default" wird in diesem Schema nicht für diesen Zweck verwendet; das Attribut `minOccurs` wird nur durch die Einstellung <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> beeinflusst und das Attribut `nillable` wird nur von dem Typ des Datenelements beeinflusst.  
  
- Den zu verwendenden tatsächlichen Standardwert gibt es in dem Schema nicht. Der empfangende Endpunkt ist dafür verantwortlich, ein fehlendes Element angemessen zu interpretieren.  
  
 Beim Schema Import wird die- <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> Eigenschaft automatisch auf festgelegt, `false` Wenn die zuvor erwähnte WCF-spezifische Anmerkung erkannt wird. Sie wird auch auf `false` für Verweis Typen festgelegt, deren- `nillable` Eigenschaft auf festgelegt ist `false` , um bestimmte Interoperabilitäts Szenarien zu unterstützen, die häufig bei der Verwendung von ASP.NET-Webdiensten  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
