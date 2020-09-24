---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 878e39af575328fb0abba096c327d36203a52231
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164804"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)

Dieser Abschnitt enthält eine Übersicht über das Erstellen des relationalen Schemas eines `DataSet` aus einem XSD-Schemadokument (XML Schema Definition Language). Im Allgemeinen wird für jedes untergeordnete `complexType` Element eines Schema Elements eine Tabelle in generiert `DataSet` . Die Tabellenstruktur wird durch die Definition des komplexen Typs festgelegt. Tabellen werden in `DataSet` für Elemente der obersten Ebene im Schema erstellt. Allerdings wird eine Tabelle nur für ein Element der obersten Ebene erstellt `complexType` , wenn das `complexType` Element in einem anderen Element geschachtelt ist `complexType` . in diesem Fall wird das geschachtelte `complexType` Element einem in `DataTable` der zugeordnet `DataSet` .  
  
 Weitere Informationen zu XSD finden Sie in der Empfehlung zum XML- [Schema Part 0: Primer](https://www.w3.org/TR/xmlschema-0/)(World Wide Web Consortium (W3C), der Empfehlung zu [XML-Schema Teil 1: Strukturen](https://www.w3.org/TR/xmlschema-1/)und der [Empfehlung XML Schema Part 2: Datatypes](https://www.w3.org/TR/xmlschema-2/).  
  
 Im folgenden Beispiel wird ein XML-Schema veranschaulicht `customers` , wobei das untergeordnete Element des- `MyDataSet` Elements ist, bei dem es sich um ein **DataSet** -Element handelt.  
  
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
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Der Datentyp jeder Spalte in der Tabelle wird aus dem XML-Schematyp des entsprechenden angegebenen Elements oder Attributs abgeleitet.  
  
> [!NOTE]
> Wenn das Element `customers` einen einfachen XML-Schema Datentyp wie " **Integer**" hat, wird keine Tabelle generiert. Tabellen werden nur für Elemente auf oberster Ebene erstellt, bei denen es sich um komplexe Typen handelt.  
  
 Im folgenden XML-Schema verfügt das **Schema** Element über zwei untergeordnete Elemente, `InStateCustomers` und `OutOfStateCustomers` .  
  
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
  
 Die beiden untergeordneten Elemente `InStateCustomers` und `OutOfStateCustomers` sind Elemente komplexen Typs (`customerType`). Aus diesem Grund generiert der Mapping-Prozess die folgenden beiden identischen Tabellen in `DataSet` .  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schema Elemente, die zum Erstellen von Unique-und FOREIGN KEY-Einschränkungen in einer verwendet werden `DataSet` .  
  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Beschreibt die XML-Schema Elemente, die zum Erstellen von Beziehungen zwischen Tabellen Spalten in einem verwendet werden `DataSet` .  
  
 [XML-Schemaeinschränkungen und -beziehungen](xml-schema-constraints-and-relationships.md)  
 Beschreibt, wie Beziehungen implizit erstellt werden, wenn XML-Schema Elemente zum Erstellen von Einschränkungen in verwendet werden `DataSet` .  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)  
 Beschreibt, wie die relationale Struktur und die Daten in als XML-Daten geladen und persistent gespeichert werden `DataSet` .  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ADO.NET](../ado-net-overview.md)
