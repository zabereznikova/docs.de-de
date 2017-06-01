---
title: "Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
In einem <xref:System.Data.DataSet> können Sie eine Verknüpfung zwischen zwei oder mehreren Spalten erstellen, indem Sie eine Beziehung zwischen übergeordneten und untergeordneten Elementen erstellen.  Es gibt drei Möglichkeiten, eine **DataSet**\-Beziehung innerhalb eines XSD\-Schemas \(XML Schema Definition Language\) darzustellen:  
  
-   Geben Sie geschachtelte komplexe Typen an.  
  
-   Verwenden Sie die **msdata:Relationship**\-Anmerkung.  
  
-   Geben Sie **xs:keyref** ohne die **msdata:ConstraintOnly**\-Anmerkung an.  
  
## Geschachtelte komplexe Typen  
 Geschachtelte komplexe Typdefinitionen in einem Schema geben die Beziehungen zwischen übergeordneten und untergeordneten Elementen an.  Im folgenden Ausschnitt eines XML\-Schemas wird dargestellt, dass **OrderDetail** ein untergeordnetes Element des **Order**\-Elements ist.  
  
```  
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
  
 Der XML\-Schemazuordnungsprozess erstellt Tabellen im **DataSet**, die den geschachtelten komplexen Typen im Schema entsprechen.  Er erstellt ebenfalls zusätzliche Spalten, die als übergeordnete **\-**und untergeordnete Spalten für die generierten Tabellen verwendet werden.  Beachten Sie, dass durch diese übergeordneten **\-**und untergeordneten Spalten Beziehungen angegeben werden. Dies ist nicht mit dem Angeben von Primärschlüssel\- und Fremdschlüsseleinschränkungen identisch.  
  
## Die "msdata:Relationship"\-Anmerkung  
 Mit der **msdata:Relationship**\-Anmerkung können Sie für nicht geschachtelte Elemente im Schema die Beziehungen zwischen übergeordneten und untergeordneten Elementen explizit angeben.  Im folgenden Beispiel wird die Struktur des **Relationship**\-Elements dargestellt.  
  
```  
  
  <msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Mit den Attributen der **msdata:Relationship**\-Anmerkung werden die einzubeziehenden Elemente für die Beziehung zwischen übergeordneten und untergeordneten Elementen sowie das **parentkey**\-Element und das **childkey**\-Element und die erforderlichen Attribute der Beziehung angegeben.  Der Zuordnungsprozess verwendet diese Informationen, um Tabellen im **DataSet** zu generieren und die Primärschlüssel\-Fremdschlüssel\-Beziehung zwischen diesen Tabellen zu erstellen.  
  
 Im folgenden Schemaausschnitt werden beispielsweise das **Order**\-Element und das **OrderDetail**\-Element auf derselben Ebene \(nicht geschachtelt\) angegeben.  In dem Schema ist eine **msdata:Relationship**\-Anmerkung angegeben, die die Beziehung zwischen übergeordneten und untergeordneten Elementen für diese beiden Elementen festlegt.  In diesem Fall muss mithilfe der **msdata:Relationship**\-Anmerkung eine explizite Beziehung angegeben werden.  
  
```  
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
  
 Der Zurordnungsprozess erstellt mit dem **Relationship**\-Element eine Beziehung zwischen übergeordneten und untergeordneten Elementen für die **OrderNumber**\-Spalte in der **Order**\-Tabelle und der **OrderNo**\-Spalte in der **OrderDetail**\-Tabelle des **DataSet**.  Der Zuordnungsprozess gibt nur die Beziehung an. Einschränkungen für die Werte in diesen Spalten werden nicht wie bei den Primärschlüssel\- und Fremdschlüsseleinschränkungen in relationalen Datenbanken automatisch angegeben.  
  
### In diesem Abschnitt  
 [Zuordnen von impliziten Beziehungen zwischen im Schema geschachtelten Elementen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 Beschreibt die Einschränkungen und Beziehungen, die implizit in einem **DataSet** erstellt werden, wenn geschachtelte Elemente im XML\-Schema vorhanden sind.  
  
 [Zuordnen von für geschachtelte Elemente angegebenen Beziehungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 Beschreibt das explizite Festlegen von Beziehungen in einem **DataSet** für geschachtelte Elemente in einem XML\-Schema.  
  
 [Angeben von Beziehungen zwischen Elementen ohne Schachtelung](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 Beschreibt das Erstellen von Beziehungen in einem **DataSet** zwischen nicht geschachtelten XML\-Schemaelementen.  
  
### Verwandte Abschnitte  
 [Ableiten einer relationalen 'DataSet'\-Struktur aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur bzw. das Schema eines **DataSet**, das aus einem XSD\-Schema \(XML Schema Definition Language\) erstellt wird.  
  
 [Zuordnen von XSD\-Einschränkungen \(XML\-Schema\) zu DataSet\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die zum Erstellen von eindeutigen Einschränkungen und Fremdschlüsseleinschränkungen in einem **DataSet** verwendeten XML\-Schemaelemente.  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)