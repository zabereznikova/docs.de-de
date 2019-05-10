---
title: Standardwerte der Datenelemente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data members [WCF], default values
- data members [WCF]
ms.assetid: 53a3b505-4b27-444b-b079-0eb84a97cfd8
ms.openlocfilehash: f92fc78aa7645abb742fdb38c360ac6641b1591d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627058"
---
# <a name="data-member-default-values"></a>Standardwerte der Datenelemente
In der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], besitzen Typen ein Konzept von *Standardwerte*. Für jeden Referenztyp ist der Standardwert beispielsweise  `null`, und für einen Integertyp ist er 0 (null). Von Zeit zu Zeit ist es empfehlenswert, ein Datenelement aus serialisierten Daten zu entfernen, wenn es auf seinen Standardwert festgelegt ist. Da das Element seinen Standardwert besitzt, braucht kein tatsächlicher Wert serialisiert werden; dies führt zu einem Leistungsvorteil.  
  
 Um ein Element aus den serialisierten Daten zu löschen, legen Sie die Eigenschaft <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> des Attributs <xref:System.Runtime.Serialization.DataMemberAttribute> auf `false` fest (der Standardwert ist `true`).  
  
> [!NOTE]
>  Sie sollten die <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>-Eigenschaft bei Bedarf auf `false` festlegen, z. B. aus Interoperabilitätsgründen oder zum Verringern der Datengröße.  
  
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
 Siehe [Versionsverwaltung von Datenverträgen](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md), <xref:System.Runtime.Serialization.DataMemberAttribute> Attribut hat eine <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> Eigenschaft (der Standardwert ist `false`). Die Eigenschaft gibt an, ob ein bestimmtes Datenelement in den serialisierten Daten vorliegen muss, wenn sie deserialisiert werden. Wenn `IsRequired` auf `true` (gibt an, dass ein Wert vorliegen muss) und <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> auf `false` festgelegt ist (gibt an, dass der Wert nicht vorliegen muss, wenn das Element auf den Standardwert festgelegt ist), können Standardwerte für dieses Datenelement nicht serialisiert werden, da die Ergebnisse widersprüchlich wären. Wenn ein derartiges Datenelement auf seinen Standardwert gesetzt ist (normalerweise `null` oder 0 (null)) und eine Serialisierung versucht wird, wird eine <xref:System.Runtime.Serialization.SerializationException> ausgelöst.  
  
### <a name="schema-representation"></a>Schemendarstellung  
 Die Details der schemadarstellung von Datenelementen XML-Schema Definition Language (XSD) bei der `EmitDefaultValue` -Eigenschaftensatz auf `false` finden Sie im [Datenvertrags-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Im Folgenden wird jedoch nur eine kurze Übersicht gegeben:  
  
- Wenn die <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> nastaven NA hodnotu `false`, es wird im Schema als eine Anmerkung, die spezifisch für Windows Communication Foundation (WCF) dargestellt. Es gibt keine interoperable Möglichkeit, diese Informationen darzustellen. Besonders das Attribut "default" wird in diesem Schema nicht für diesen Zweck verwendet; das Attribut `minOccurs` wird nur durch die Einstellung <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> beeinflusst und das Attribut `nillable` wird nur von dem Typ des Datenelements beeinflusst.  
  
- Den zu verwendenden tatsächlichen Standardwert gibt es in dem Schema nicht. Der empfangende Endpunkt ist dafür verantwortlich, ein fehlendes Element angemessen zu interpretieren.  
  
 Beim schemenimport der <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> Eigenschaft wird automatisch festgelegt, um `false` jedes Mal, wenn die WCF-spezifische Anmerkung erwähnt zuvor erkannt wird. Außerdem wird sie für Referenztypen auf `false` festgelegt, deren Eigenschaft `nillable` auf  `false` festgelegt ist, um spezielle Interoperabilitätsszenarien zu unterstützen, die häufig bei der Nutzung von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webdiensten auftreten.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
