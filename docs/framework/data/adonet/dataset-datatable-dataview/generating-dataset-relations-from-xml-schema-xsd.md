---
title: Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: 29c0e9ee96c376c6da392692febccbbae3c6a33f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034319"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
In einem <xref:System.Data.DataSet> können Sie eine Verknüpfung zwischen zwei oder mehreren Spalten erstellen, indem Sie eine Beziehung zwischen übergeordneten und untergeordneten Elementen erstellen. Es gibt drei Möglichkeiten zur Darstellung einer **DataSet** Beziehung in ein Schema für XML Schema Definition Language (XSD):  
  
- Geben Sie geschachtelte komplexe Typen an.  
  
- Verwenden der **msdata: Relationship** Anmerkung.  
  
- Geben Sie eine **xs: keyref** ohne die **msdata: ConstraintOnly** Anmerkung.  
  
## <a name="nested-complex-types"></a>Geschachtelte komplexe Typen  
 Geschachtelte komplexe Typdefinitionen in einem Schema geben die Beziehungen zwischen übergeordneten und untergeordneten Elementen an. Das folgende XML-Schema-Fragment zeigt, dass **OrderDetail** ist ein untergeordnetes Element von der **Reihenfolge** Element.  
  
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
  
 Die XML-Schemazuordnungsprozess erstellt Tabellen in der **DataSet** , die den geschachtelten komplexen Typen im Schema entsprechen. Er erstellt ebenfalls zusätzliche Spalten, die als übergeordnetes Element verwendet werden**-** untergeordnete Spalten für die generierten Tabellen. Beachten Sie, die diese übergeordneten**-** untergeordneten Spalten Beziehungen, das ist nicht derselbe, als wenn primary Key/foreign Key-Einschränkungen angegeben.  
  
## <a name="msdatarelationship-annotation"></a>Die "msdata:Relationship"-Anmerkung  
 Die **msdata: Relationship** -Anmerkung können Sie explizit die über-/ unterordnungsbeziehung zwischen den Elementen im Schema angeben, die nicht geschachtelt sind. Das folgende Beispiel zeigt die Struktur der **Beziehung** Element.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Die Attribute der **msdata: Relationship** Anmerkung zu identifizieren, die Elemente für die über-/ unterordnungsbeziehung ist, werden auch als die **Parentkey** und **Childkey** Elemente und Attribute der Beziehung beteiligt. Der Zuordnungsprozess verwendet diese Informationen zum Generieren von Tabellen in der **DataSet** und die primary Key/Fremdschlüssel-Beziehung zwischen diesen Tabellen zu erstellen.  
  
 Das folgende Schemafragment gibt z. B. **Reihenfolge** und **OrderDetail** Elemente auf derselben Ebene (nicht geschachtelt). Das Schema gibt ein **msdata: Relationship** Anmerkung, die angibt, die über-/ unterordnungsbeziehung zwischen diesen beiden Elementen. In diesem Fall eine explizite Beziehung angegeben werden mithilfe der **msdata: Relationship** Anmerkung.  
  
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
  
 Der Zuordnungsprozess verwendet die **Beziehung** Element zum Erstellen einer über-/ unterordnungsbeziehung zwischen den **OrderNumber** -Spalte in der **Reihenfolge** Tabelle und die **OrderNo** -Spalte in der **OrderDetail** -Tabelle in der **DataSet**. Der Zuordnungsprozess gibt nur die Beziehung an. Einschränkungen für die Werte in diesen Spalten werden nicht wie bei den Primärschlüssel- und Fremdschlüsseleinschränkungen in relationalen Datenbanken automatisch angegeben.  
  
### <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 Beschreibt die Einschränkungen und Beziehungen, die implizit in erstellt werden ein **DataSet** Wenn geschachtelte Elemente im XML-Schema gefunden werden.  
  
 [Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 Beschreibt, wie Sie das explizite Festlegen von Beziehungen einem **DataSet** für geschachtelte Elemente im XML-Schema.  
  
 [Angeben von Beziehungen zwischen Elementen ohne Schachtelung](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 Beschreibt das Erstellen von Beziehungen in einem **DataSet** zwischen XML-Schema-Elemente, die nicht geschachtelt sind.  
  
### <a name="related-sections"></a>Verwandte Abschnitte  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur bzw. das Schema, der eine **DataSet** , die vom Schema der XML Schema Definition Language (XSD) erstellt wird.  
  
 [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schema-Elemente, die zum Erstellen von Unique- und foreign Key-Einschränkungen in einer **DataSet**.  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
