---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d15aa02b41b9a34b00298aeb32d2e3998de8feba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786333"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
Dieser Abschnitt enthält eine Übersicht über das Erstellen des relationalen Schemas eines `DataSet` aus einem XSD-Schemadokument (XML Schema Definition Language). Im Allgemeinen wird für jedes `complexType` untergeordnete Element eines Schema Elements eine Tabelle `DataSet`in generiert. Die Tabellenstruktur wird durch die Definition des komplexen Typs festgelegt. Tabellen werden in `DataSet` für Elemente der obersten Ebene im Schema erstellt. Allerdings wird eine Tabelle nur für ein Element der obersten Ebene `complexType` erstellt, wenn `complexType` das `complexType` Element in einem anderen `complexType` Element geschachtelt ist. in diesem Fall wird das geschachtelte `DataTable` Element einem `DataSet`in der zugeordnet.  
  
 Weitere Informationen zu XSD finden Sie in der World Wide Web Consortium (W3C) [XML Schema Part 0: Empfehlung](https://www.w3.org/TR/xmlschema-0/)für das [XML-Schema Teil 1: Struktur Empfehlung](https://www.w3.org/TR/xmlschema-1/)und das [XML-Schema Teil 2: Empfehlungen zu Datentypen](https://www.w3.org/TR/xmlschema-2/).  
  
 Im folgenden Beispiel wird ein XML-Schema `customers` veranschaulicht, wobei das untergeordnete `MyDataSet` Element des-Elements ist, bei dem es sich um ein **DataSet** -Element handelt.  
  
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
> Wenn das Element `customers` einen einfachen XML-Schema Datentyp wie " **Integer**" hat, wird keine Tabelle generiert. Tabellen werden nur für Elemente auf oberster Ebene erstellt, bei denen es sich um komplexe Typen handelt.  
  
 Im folgenden XML-Schema verfügt das **Schema** Element über zwei untergeordnete Elemente `InStateCustomers` , `OutOfStateCustomers`und.  
  
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
  
 Die beiden untergeordneten Elemente `InStateCustomers` und `OutOfStateCustomers` sind Elemente komplexen Typs (`customerType`). Aus diesem Grund generiert der Mapping-Prozess die folgenden beiden identischen Tabellen `DataSet`in.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schema Elemente, die zum Erstellen von Unique-und Foreign `DataSet`Key-Einschränkungen in einer verwendet werden.  
  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Beschreibt die XML-Schema Elemente, die zum Erstellen von Beziehungen zwischen Tabellen `DataSet`Spalten in einem verwendet werden.  
  
 [XML-Schemaeinschränkungen und -beziehungen](xml-schema-constraints-and-relationships.md)  
 Beschreibt, wie Beziehungen implizit erstellt werden, wenn XML-Schema Elemente zum Erstellen von `DataSet`Einschränkungen in verwendet werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)  
 Beschreibt, wie die relationale Struktur und die Daten in `DataSet` als XML-Daten geladen und persistent gespeichert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](../ado-net-overview.md)
