---
title: "Ableiten einer relationalen &#39;DataSet&#39;-Struktur aus einem XML-Schema (XSD) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Ableiten einer relationalen &#39;DataSet&#39;-Struktur aus einem XML-Schema (XSD)
Dieser Abschnitt enthält eine Übersicht über das Erstellen des relationalen Schemas eines <xref:System.Data.DataSet> aus einem XSD\-Schemadokument \(XML Schema Definition Language\).  Im Allgemeinen wird für jedes untergeordnete **complexType**\-Element eines Schemaelements eine Tabelle im **DataSet** generiert.  Die Tabellenstruktur wird durch die Definition des komplexen Typs festgelegt.  Tabellen werden im **DataSet** für Elemente auf der obersten Ebene des Schemas erstellt.  Allerdings werden Tabellen für **complexType**\-Elemente auf der obersten Ebene nur dann erstellt, wenn das **complexType**\-Element in einem anderen **complexType**\-Element geschachtelt ist. In diesem Fall wird das geschachtelte **complexType**\-Element einer <xref:System.Data.DataTable> in einem **DataSet** zugeordnet.  
  
 Weitere Informationen zu XSD finden Sie in der Empfehlung des W3C \(World Wide Web Consortium\) unter "XML Schema Part 0: Primer" und "XML Schema Part 1: Structures" sowie unter "XML Schemas Part 2: Datatypes" unter [http:\/\/www.w3.org\/](http://www.w3.org/TR/).  
  
 Im folgenden Beispiel wird ein XML\-Schema veranschaulicht, bei dem `customers` das dem **DataSet**\-Element `MyDataSet` untergeordnete Element ist.  
  
```  
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
  
 Im vorherigen Beispiel ist das `customers`\-Element ein Element mit komplexem Typ.  Daher wird die Definition des komplexen Typs analysiert, und der Zuordnungsprozess erstellt die folgende Tabelle.  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 Der Datentyp jeder Spalte in der Tabelle wird aus dem XML\-Schematyp des entsprechenden angegebenen Elements oder Attributs abgeleitet.  
  
> [!NOTE]
>  Wenn das `customers`\-Element einen einfachen XML\-Schematyp aufweist, z. B. **integer**, wird keine Tabelle generiert.  Tabellen werden nur für Elemente auf oberster Ebene erstellt, bei denen es sich um komplexe Typen handelt.  
  
 Im folgenden XML\-Schema weist das **Schema**\-Element die folgenden zwei untergeordneten Elemente auf: `InStateCustomers` und `OutOfStateCustomers`.  
  
```  
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
  
 Die beiden untergeordneten Elemente `InStateCustomers` und `OutOfStateCustomers` sind Elemente komplexen Typs \(`customerType`\).  Der Zuordnungsvorgang generiert daher die folgenden zwei identischen Tabellen im **DataSet**.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## In diesem Abschnitt  
 [Zuordnen von XSD\-Einschränkungen \(XML\-Schema\) zu DataSet\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Beschreibt die zum Erstellen von eindeutigen Einschränkungen und Fremdschlüsseleinschränkungen in einem **DataSet** verwendeten XML\-Schemaelemente.  
  
 [Generieren von DataSet\-Beziehungen aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Beschreibt die zum Erstellen von Beziehungen zwischen Tabellenspalten in einem **DataSet** verwendeten XML\-Schemaelemente.  
  
 [Einschränkungen und Beziehungen in einem XML\-Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 Beschreibt das implizite Erstellen von Beziehungen, wenn mit XML\-Schemaelementen Einschränkungen in einem **DataSet** erstellt werden.  
  
## Verwandte Abschnitte  
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Beschreibt, wie die relationale Struktur und die Daten in einem **DataSet** als XML\-Daten geladen und beibehalten werden.  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)