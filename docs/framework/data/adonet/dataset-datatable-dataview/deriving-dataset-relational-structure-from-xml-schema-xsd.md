---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d32b5cb86bc5a138f9a5f438629d8e231be4ba94
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151168"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
Dieser Abschnitt enthält eine Übersicht über das Erstellen des relationalen Schemas eines `DataSet` aus einem XSD-Schemadokument (XML Schema Definition Language). Im Allgemeinen wird `complexType` für jedes untergeordnete Element eines Schemaelements `DataSet`eine Tabelle im generiert. Die Tabellenstruktur wird durch die Definition des komplexen Typs festgelegt. Tabellen werden in `DataSet` der für Elemente der obersten Ebene im Schema erstellt. Eine Tabelle wird jedoch nur für `complexType` ein Element `complexType` der obersten Ebene `complexType` erstellt, wenn das `complexType` Element in einem `DataTable` anderen `DataSet`Element verschachtelt ist.  
  
 Weitere Informationen zum XSD finden Sie im [XML-Schema-Teil 0: Primer-Schema-Teil 0: Primer-Schema](https://www.w3.org/TR/xmlschema-0/), [im XML-Schema Teil 1: Structures-Empfehlung](https://www.w3.org/TR/xmlschema-1/)und in der [XML-Schema-Empfehlung 2: Datentypen-](https://www.w3.org/TR/xmlschema-2/)  
  
 Im folgenden Beispiel wird `customers` ein XML-Schema `MyDataSet` veranschaulicht, bei dem es sich um das untergeordnete Element des Elements handelt, bei dem es sich um ein **DataSet-Element** handelt.  
  
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
> Wenn das `customers` Element aus einem einfachen XML-Schema-Datentyp wie **Ganzzahl**ist, wird keine Tabelle generiert. Tabellen werden nur für Elemente auf oberster Ebene erstellt, bei denen es sich um komplexe Typen handelt.  
  
 Im folgenden XML-Schema enthält das **Schemaelement** zwei untergeordnete Elementelemente `InStateCustomers` und `OutOfStateCustomers`.  
  
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
  
 Die beiden untergeordneten Elemente `InStateCustomers` und `OutOfStateCustomers` sind Elemente komplexen Typs (`customerType`). Daher generiert der Zuordnungsprozess die folgenden `DataSet`beiden identischen Tabellen im .  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die XML-Schemaelemente, die zum Erstellen `DataSet`eindeutiger und Fremdschlüsseleinschränkungen in einem verwendet werden.  
  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Beschreibt die XML-Schemaelemente, die zum `DataSet`Erstellen von Beziehungen zwischen Tabellenspalten in einem verwendet werden.  
  
 [XML-Schemaeinschränkungen und -beziehungen](xml-schema-constraints-and-relationships.md)  
 Beschreibt, wie Beziehungen implizit erstellt werden, wenn XML-Schemaelemente zum Erstellen von Einschränkungen in einem `DataSet`erstellt werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verwenden von XML in einem "DataSet"](using-xml-in-a-dataset.md)  
 Beschreibt das Laden und Beibehalten der relationalen Struktur und der Daten in einem `DataSet` als XML-Daten.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ADO.NET](../ado-net-overview.md)
