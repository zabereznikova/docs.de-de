---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 7599577c4e0f485e336e7f79a6c3bd17f0f0c316
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759607"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
Dieser Abschnitt enthält eine Übersicht über das Erstellen des relationalen Schemas eines `DataSet` aus einem XSD-Schemadokument (XML Schema Definition Language). Im Allgemeinen wird für jede `complexType` untergeordnetes Element eines Schemaelements eine Tabelle wird generiert, der `DataSet`. Die Tabellenstruktur wird durch die Definition des komplexen Typs festgelegt. Tabellen werden erstellt, der `DataSet` für Elemente der obersten Ebene im Schema. Allerdings wird eine Tabelle nur für ein auf oberster Ebene erstellt `complexType` Element bei der `complexType` in einem anderen Element geschachtelt ist `complexType` Element, in dem Fall wird das geschachtelte `complexType` Element zugeordnet ist ein `DataTable` innerhalb der `DataSet`.  
  
 Weitere Informationen zu XSD finden Sie unter der World Wide Web Consortium (W3C) XML Schema Part 0: Primer Empfehlung, die XML Schema Part 1: Strukturempfehlung und die XML Schema Part 2: Datatypes Recommendation, am [ http://www.w3.org/ ](http://www.w3.org/TR/).  
  
 Das folgende Beispiel zeigt ein XML-Schema, in dem `customers` ist das untergeordnete Element von der `MyDataSet` Elements, d. h. eine **DataSet** Element.  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 Im vorherigen Beispiel ist das `customers`-Element ein Element mit komplexem Typ. Daher wird die Definition des komplexen Typs analysiert, und der Zuordnungsprozess erstellt die folgende Tabelle.  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 Der Datentyp jeder Spalte in der Tabelle wird aus dem XML-Schematyp des entsprechenden angegebenen Elements oder Attributs abgeleitet.  
  
> [!NOTE]
>  Wenn das Element `customers` eines einfachen Datentyps von XML-Schema handelt, z. B. **Ganzzahl**, keine Tabelle generiert. Tabellen werden nur für Elemente auf oberster Ebene erstellt, bei denen es sich um komplexe Typen handelt.  
  
 Im folgenden XML-Schema das **Schema** Element verfügt über zwei untergeordneten Elemente auf: `InStateCustomers` und `OutOfStateCustomers`.  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 Die beiden untergeordneten Elemente `InStateCustomers` und `OutOfStateCustomers` sind Elemente komplexen Typs (`customerType`). Der Zuordnungsvorgang generiert daher die folgenden zwei identischen Tabellen in der `DataSet`.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schema-Elemente, die zum Erstellen von Unique- und foreign Key-Einschränkungen in einer `DataSet`.  
  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Beschreibt die XML-Schema-Elemente, die zum Erstellen von Beziehungen zwischen Tabellenspalten in einer `DataSet`.  
  
 [XML-Schemaeinschränkungen und -beziehungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 Beschreibt, wie Beziehungen implizit erstellt werden, wenn XML-Schemaelementen Einschränkungen in einer `DataSet`.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Beschreibt, wie geladen und beibehalten, die relationale Struktur und die Daten in einem `DataSet` als XML-Daten.  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
