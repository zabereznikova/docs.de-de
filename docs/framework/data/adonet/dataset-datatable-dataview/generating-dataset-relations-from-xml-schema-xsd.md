---
title: Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: 2673280ebb94dcc10c130f3969f3e3250d3706a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198586"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)

In einem <xref:System.Data.DataSet> können Sie eine Verknüpfung zwischen zwei oder mehreren Spalten erstellen, indem Sie eine Beziehung zwischen übergeordneten und untergeordneten Elementen erstellen. Es gibt drei Möglichkeiten, eine **datasetbeziehung** innerhalb eines XSD-Schemas (XML Schema Definition Language) darzustellen:  
  
- Geben Sie geschachtelte komplexe Typen an.  
  
- Verwenden Sie die **msdata: Relationship** -Anmerkung.  
  
- Geben Sie einen **xs: keyref** ohne die " **msdata: einschränintonly** "-Anmerkung an.  
  
## <a name="nested-complex-types"></a>Geschachtelte komplexe Typen  

 Geschachtelte komplexe Typdefinitionen in einem Schema geben die Beziehungen zwischen übergeordneten und untergeordneten Elementen an. Das folgende XML-Schema Fragment zeigt, dass **OrderDetail** ein untergeordnetes Element des **Order** -Elements ist.  
  
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
  
 Der Prozess für die XML-Schema Zuordnung erstellt Tabellen im **DataSet** , die den im Schema erstellten komplexen Typen entsprechen. Außerdem werden zusätzliche Spalten erstellt, die als übergeordnete **-** untergeordnete Spalten für die generierten Tabellen verwendet werden. Beachten Sie, dass diese übergeordneten **-** untergeordneten Spalten Beziehungen angeben. Dies entspricht nicht der Angabe von PRIMARY KEY/FOREIGN KEY-Einschränkungen.  
  
## <a name="msdatarelationship-annotation"></a>Die "msdata:Relationship"-Anmerkung  

 Mithilfe der **msdata: Relationship** -Anmerkung können Sie explizit Beziehungen zwischen übergeordneten und untergeordneten Elementen zwischen Elementen im Schema angeben, die nicht schzistet sind. Das folgende Beispiel zeigt die Struktur des **Relationship** -Elements.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 Die Attribute der **msdata: Relationship** -Anmerkung identifizieren die Elemente, die an der Beziehung zwischen übergeordneten **und untergeordneten** Elementen beteiligt sind, sowie die Elemente und Attribute von "arkey" und " **childkey** ", die an der Beziehung beteiligt sind. Der Mapping-Prozess verwendet diese Informationen zum Generieren von Tabellen im **DataSet** und zum Erstellen der Primärschlüssel-/Fremdschlüssel Beziehung zwischen diesen Tabellen.  
  
 Das folgende Schema Fragment gibt z. b. **Order** -und **Order Detail** -Elemente auf derselben Ebene an (nicht schsted). Das Schema gibt eine **msdata: Relationship** -Anmerkung an, die die über-/Unterordnungsbeziehung zwischen diesen beiden Elementen angibt. In diesem Fall muss mithilfe der **msdata: Relationship** -Anmerkung eine explizite Beziehung angegeben werden.  
  
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
  
 Der Mapping-Prozess verwendet das **Relationship** -Element, um eine über-/Unterordnungsbeziehung zwischen der **OrderNumber** -Spalte in der **Order** -Tabelle und der **OrderNo** -Spalte in der **Order Detail** -Tabelle des **DataSets**zu erstellen. Der Zuordnungsprozess gibt nur die Beziehung an. Einschränkungen für die Werte in diesen Spalten werden nicht wie bei den Primärschlüssel- und Fremdschlüsseleinschränkungen in relationalen Datenbanken automatisch angegeben.  
  
### <a name="in-this-section"></a>In diesem Abschnitt  

 [Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen](map-implicit-relations-between-nested-schema-elements.md)  
 Beschreibt die Einschränkungen und Beziehungen, die implizit in einem **DataSet** erstellt werden, wenn in einem XML-Schema schsted Elemente gefunden werden.  
  
 [Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind](map-relations-specified-for-nested-elements.md)  
 Beschreibt, wie Beziehungen in einem **DataSet** für in einem XML-Schema eingested Elemente explizit festgelegt werden.  
  
 [Angeben von Beziehungen zwischen Elementen ohne Verschachtelung](specify-relations-between-elements-with-no-nesting.md)  
 Beschreibt, wie Beziehungen in einem **DataSet** zwischen XML-Schema Elementen erstellt werden, die nicht scht sind.  
  
### <a name="related-sections"></a>Verwandte Abschnitte  

 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur bzw. das Schema eines **DataSets** , das aus einem XSD-Schema (XML Schema Definition Language) erstellt wird.  
  
 [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schema Elemente, die zum Erstellen von Unique-und FOREIGN KEY-Einschränkungen in einem **DataSet**verwendet werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ADO.NET](../ado-net-overview.md)
