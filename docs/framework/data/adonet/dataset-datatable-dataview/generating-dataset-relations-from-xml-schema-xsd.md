---
title: Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151129"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
In einem <xref:System.Data.DataSet> können Sie eine Verknüpfung zwischen zwei oder mehreren Spalten erstellen, indem Sie eine Beziehung zwischen übergeordneten und untergeordneten Elementen erstellen. Es gibt drei Möglichkeiten, eine **DataSet-Beziehung** innerhalb eines XSD-Schemas (XML Schema Definition Language) darzustellen:  
  
- Geben Sie geschachtelte komplexe Typen an.  
  
- Verwenden Sie die **Msdata:Relationship-Anmerkung.**  
  
- Geben Sie eine **xs:keyref** ohne die **msdata:ConstraintOnly-Anmerkung** an.  
  
## <a name="nested-complex-types"></a>Geschachtelte komplexe Typen  
 Geschachtelte komplexe Typdefinitionen in einem Schema geben die Beziehungen zwischen übergeordneten und untergeordneten Elementen an. Das folgende XML-Schemafragment zeigt, dass **OrderDetail** ein untergeordnetes Element des **Order-Elements** ist.  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>
       <xs:element name="OrderDetail" />  
           <xs:complexType>
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Der XML-Schemazuordnungsprozess erstellt Tabellen im **DataSet,** die den geschachtelten komplexen Typen im Schema entsprechen. Außerdem werden zusätzliche Spalten erstellt,**-** die als übergeordnete untergeordnete Spalten für die generierten Tabellen verwendet werden. Beachten Sie,**-** dass diese übergeordneten untergeordneten Spalten Beziehungen angeben, die nicht mit der Angabe von Primärschlüssel-/Fremdschlüsseleinschränkungen identisch sind.  
  
## <a name="msdatarelationship-annotation"></a>Die "msdata:Relationship"-Anmerkung  
 Mit der **msdata:Relationship-Anmerkung** können Sie explizit parent-child-Beziehungen zwischen Elementen im Schema angeben, die nicht geschachtelt sind. Das folgende Beispiel zeigt **Relationship** die Struktur des Beziehungselements.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 Die Attribute der **msdata:Relationship-Anmerkung** identifizieren die Elemente, die an der Eltern-Kind-Beziehung beteiligt sind, sowie die Elemente und Attribute des **übergeordneten Schlüssels** und des **untergeordneten Schlüssels** und attribute, die an der Beziehung beteiligt sind. Der Zuordnungsprozess verwendet diese Informationen, um Tabellen im **DataSet** zu generieren und die Primärschlüssel-/Fremdschlüsselbeziehung zwischen diesen Tabellen zu erstellen.  
  
 Das folgende Schemafragment gibt z. B. **Order-** und **OrderDetail-Elemente** auf derselben Ebene (nicht geschachtelt) an. Das Schema gibt eine **msdata:Relationship-Anmerkung** an, die die Parent-Child-Beziehung zwischen diesen beiden Elementen angibt. In diesem Fall muss eine explizite Beziehung mithilfe der **msdata:Relationship-Anmerkung** angegeben werden.  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 Der Zuordnungsprozess verwendet das Relationship-Element, um eine Parent-Child-Beziehung zwischen der **OrderNumber-Spalte** in der **Tabelle Order** und der **OrderNo-Spalte** in der **Tabelle OrderDetail** im **DataSet**zu erstellen. **Relationship** Der Zuordnungsprozess gibt nur die Beziehung an. Einschränkungen für die Werte in diesen Spalten werden nicht wie bei den Primärschlüssel- und Fremdschlüsseleinschränkungen in relationalen Datenbanken automatisch angegeben.  
  
### <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen](map-implicit-relations-between-nested-schema-elements.md)  
 Beschreibt die Einschränkungen und Beziehungen, die implizit in einem **DataSet** erstellt werden, wenn verschachtelte Elemente im XML-Schema gefunden werden.  
  
 [Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind](map-relations-specified-for-nested-elements.md)  
 Beschreibt, wie Beziehungen in einem **DataSet** für geschachtelte Elemente im XML-Schema explizit festgelegt werden.  
  
 [Angeben von Beziehungen zwischen Elementen ohne Verschachtelung](specify-relations-between-elements-with-no-nesting.md)  
 Beschreibt, wie Beziehungen in einem **DataSet** zwischen XML-Schemaelementen erstellt werden, die nicht geschachtelt sind.  
  
### <a name="related-sections"></a>Verwandte Abschnitte  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur oder das Schema eines **DataSets,** das aus dem Xml Schema der Schemadefinitionssprache (XSD) erstellt wird.  
  
 [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schemaelemente, die zum Erstellen eindeutiger und Fremdschlüsseleinschränkungen in einem **DataSet**verwendet werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ADO.NET](../ado-net-overview.md)
