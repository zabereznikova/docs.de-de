---
title: "Standardwerte der Datenelemente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Datenelemente [WCF]"
  - "Datenelemente [WCF], Standardwerte"
ms.assetid: 53a3b505-4b27-444b-b079-0eb84a97cfd8
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Standardwerte der Datenelemente
Im [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] besitzen Typen ein Konzept von *Standardwerten*.Für jeden Referenztyp ist der Standardwert beispielsweise  `null`, und für einen Integertyp ist er 0 \(null\).Von Zeit zu Zeit ist es empfehlenswert, ein Datenelement aus serialisierten Daten zu entfernen, wenn es auf seinen Standardwert festgelegt ist.Da das Element seinen Standardwert besitzt, braucht kein tatsächlicher Wert serialisiert werden; dies führt zu einem Leistungsvorteil.  
  
 Um ein Element aus den serialisierten Daten zu löschen, legen Sie die Eigenschaft <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> des Attributs <xref:System.Runtime.Serialization.DataMemberAttribute> auf `false` fest \(der Standardwert ist `true`\).  
  
> [!NOTE]
>  Sie sollten die <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>\-Eigenschaft auf `false` festlegen, wenn eine bestimmte Notwendigkeit dafür besteht, z. B. aus Interoperabilitätsgründen oder zum Verringern der Datengröße.  
  
## Beispiel  
 Der folgende Code verfügt über mehrere Elemente, deren <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> auf `false` festgelegt ist.  
  
 [!code-csharp[DataMemberAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/datamemberattribute/cs/overview.cs#4)]
 [!code-vb[DataMemberAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datamemberattribute/vb/overview.vb#4)]  
  
 Wenn eine Instanz dieser Klasse serialisiert wird, ergibt sich folgendes Ergebnis: `employeeName` und `employeeID` sind serialisiert.Der Nullwert für `employeeName` und der Nullwert für `employeeID` sind ausdrücklich Teil der serialisierten Daten.Die Elemente `position`, `salary` und `bonus` sind hingegen nicht serialisiert.`targetSalary` wird wie gewöhnlich serialisiert, auch wenn die <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>\-Eigenschaft auf `false` festgelegt ist, da "57800" nicht mit dem .NET\-Standardwert einer ganzen Zahl \("0"\) übereinstimmt.  
  
### XML\-Darstellung  
 Wenn das vorherige Beispiel nach XML serialisiert wird, ähnelt die Darstellung Folgendem:  
  
```  
<Employee>  
   <employeeName xsi:nil="true" />  
   <employeeID>0</employeeID>  
<targetSalary>57800</targetSalary>  
</Employee>  
```  
  
 Das Attribut `xsi:nil` ist ein Spezialattribut im XML\-Schemainstanz\-Namespace des World Wide Web Consortium \(W3C\), der eine interoperable Möglichkeit bietet, speziell einen Nullwert darzustellen.Bitte beachten Sie, dass es im XML keinerlei Informationen über die Datenelemente Position, Gehalt und Bonus gibt.Die Emfangsseite kann diese als `null`, Null bzw. `null` interpretieren.Es gibt keine Garantie, dass einem Fremdanbieterdeserialisierer eine korrekte Auslegung gelingt; daher wird dieses Muster nicht empfohlen.Die Klasse <xref:System.Runtime.Serialization.DataContractSerializer> wählt immer die richtige Auslegung für fehlende Werte.  
  
### Interaktion mit IsRequired  
 Wie in [Datenvertragsversionsverwaltung](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md) erläutert, verfügt das Attribut <xref:System.Runtime.Serialization.DataMemberAttribute> über eine Eigenschaft <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> \(der Standard ist `false`\).Die Eigenschaft gibt an, ob ein bestimmtes Datenelement in den serialisierten Daten vorliegen muss, wenn sie deserialisiert werden.Wenn `IsRequired` auf `true` \(gibt an, dass ein Wert vorliegen muss\) und <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> auf `false` festgelegt ist \(gibt an, dass der Wert nicht vorliegen muss, wenn das Element auf den Standardwert festgelegt ist\), können Standardwerte für dieses Datenelement nicht serialisiert werden, da die Ergebnisse widersprüchlich wären.Wenn ein derartiges Datenelement auf seinen Standardwert gesetzt ist \(normalerweise `null` oder 0 \(null\)\) und eine Serialisierung versucht wird, wird eine <xref:System.Runtime.Serialization.SerializationException> ausgelöst.  
  
### Schemendarstellung  
 Die Details der Schemadarstellung von Datenelementen der XML Schema\-Definitionssprache \(XSD\) bei Festlegung der Eigenschaft `EmitDefaultValue` auf `false` werden in [Datenvertrags\-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md) untersucht.Im Folgenden wird jedoch nur eine kurze Übersicht gegeben:  
  
-   Wenn <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> auf `false` festgelegt ist, wird es im Schema als eine Anmerkung, die spezifisch für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist, dargestellt.Es gibt keine interoperable Möglichkeit, diese Informationen darzustellen.Besonders das Attribut "default" wird in diesem Schema nicht für diesen Zweck verwendet; das Attribut `minOccurs` wird nur durch die Einstellung <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> beeinflusst und das Attribut `nillable` wird nur von dem Typ des Datenelements beeinflusst.  
  
-   Den zu verwendenden tatsächlichen Standardwert gibt es in dem Schema nicht.Der empfangende Endpunkt ist dafür verantwortlich, ein fehlendes Element angemessen zu interpretieren.  
  
 Beim Schemenimport wird die Eigenschaft <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> automatisch immer dann auf  `false` festgelegt, wenn die zuvor erwähnte,  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-spezifische Anmerkung gefunden wird.Außerdem wird sie für Referenztypen auf `false` festgelegt, deren Eigenschaft `nillable` auf  `false` festgelegt ist, um spezielle Interoperabilitätsszenarien zu unterstützen, die häufig bei der Nutzung von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Webdiensten auftreten.  
  
## Siehe auch  
 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>