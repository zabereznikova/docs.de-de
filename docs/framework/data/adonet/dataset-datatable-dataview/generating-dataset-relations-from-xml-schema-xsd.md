---
title: Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: fdf22c311ef7b4267f4a4da8566e4ea59504b103
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
In einem <xref:System.Data.DataSet> können Sie eine Verknüpfung zwischen zwei oder mehreren Spalten erstellen, indem Sie eine Beziehung zwischen übergeordneten und untergeordneten Elementen erstellen. Es gibt drei Möglichkeiten zur Darstellung einer **DataSet** Beziehung in einem Schema für XML Schema Definition Language (XSD):  
  
-   Geben Sie geschachtelte komplexe Typen an.  
  
-   Verwenden der **msdata: Relationship** Anmerkung.  
  
-   Geben Sie eine **xs: keyref** ohne die **msdata: ConstraintOnly** Anmerkung.  
  
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
  
 Die XML-Schemazuordnungsprozess erstellt Tabellen in der **DataSet** , die den geschachtelten komplexen Typen im Schema entsprechen. Er erstellt ebenfalls zusätzliche Spalten, die als übergeordnete verwendet**-** untergeordnete Spalten für die generierten Tabellen. Beachten Sie, die diese übergeordneten**-** untergeordneten Spalten Beziehungen ist derselbe, als wenn primary Key/foreign Key-Einschränkungen angegeben.  
  
## <a name="msdatarelationship-annotation"></a>Die "msdata:Relationship"-Anmerkung  
 Die **msdata: Relationship** -Anmerkung können Sie explizit die über-/ unterordnungsbeziehungen zwischen Elementen im Schema angeben, die nicht geschachtelt sind. Das folgende Beispiel zeigt die Struktur der **Beziehung** Element.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Die Attribute der **msdata: Relationship** Anmerkung identifizieren die Elemente für die über-und untergeordneten Elementen sowie als die **Parentkey** und **Childkey** Elemente und Attribute, die an der Beziehung beteiligte. Der Zuordnungsprozess verwendet diese Informationen zum Generieren von Tabellen in der **DataSet** und den primäre Schlüssel/Fremdschlüssel-Beziehung zwischen diesen Tabellen zu erstellen.  
  
 Das folgende Schemafragment gibt z. B. **Reihenfolge** und **OrderDetail** Elemente auf derselben Ebene (nicht geschachtelt). Das Schema gibt ein **msdata: Relationship** Anmerkung, der angibt, die über-/ unterordnungsbeziehung zwischen diesen beiden Elementen. In diesem Fall eine explizite Beziehung angegeben werden mithilfe der **msdata: Relationship** Anmerkung.  
  
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
  
 Der Zuordnungsprozess verwendet die **Beziehung** Element zum Erstellen einer über-/ unterordnungsbeziehung zwischen den **OrderNumber** Spalte in der **Reihenfolge** Tabelle und die **OrderNo** Spalte in der **OrderDetail** -Tabelle in der **DataSet**. Der Zuordnungsprozess gibt nur die Beziehung an. Einschränkungen für die Werte in diesen Spalten werden nicht wie bei den Primärschlüssel- und Fremdschlüsseleinschränkungen in relationalen Datenbanken automatisch angegeben.  
  
### <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 Beschreibt die Einschränkungen und Beziehungen, die implizit in erstellt werden ein **DataSet** Wenn geschachtelte Elemente im XML-Schema gefunden werden.  
  
 [Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 Beschreibt das explizite Festlegen von Beziehungen einem **DataSet** für geschachtelte Elemente im XML-Schema.  
  
 [Angeben von Beziehungen zwischen Elementen ohne Schachtelung](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 Enthält Informationen zum Erstellen von Beziehungen in einem **DataSet** zwischen XML-Schemaelemente, die nicht geschachtelt sind.  
  
### <a name="related-sections"></a>Verwandte Abschnitte  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur bzw. das Schema von einem **DataSet** , die vom Schema für XML Schema Definition Language (XSD) erstellt wird.  
  
 [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schema-Elemente, die zum Erstellen von Unique- und foreign Key-Einschränkungen in einer **DataSet**.  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
