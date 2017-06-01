---
title: "Erstellen stark typisierter &#39;DataSets&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Erstellen stark typisierter &#39;DataSets&#39;
Bei einem XML\-Schema, das dem XSD\-Standard \(XML Schema Definition Language\) entspricht, können Sie mit dem Tool \<legacyBold\>XSD.exe\<\/legacyBold\>, das zusammen mit dem [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)] ausgeliefert wird, ein stark typisiertes <xref:System.Data.DataSet> generieren.  
  
 \(Informationen zur XSD\-Erstellung unter Verwendung von Datenbanktabellen finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [Arbeiten mit Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)\).  
  
 Im folgenden Codebeispiel wird die Syntax dargestellt, die zum Generieren eines **DataSet** mithilfe dieses Tools verwendet wird.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 Bei dieser Syntax weist die `/d`\-Direktive das Tool an, ein **DataSet** zu generieren, und die `/l:`\-Direktive gibt die zu verwendende Programmiersprache an \(z. B. C\# oder Visual Basic .NET\).  Die optionale `/eld`\-Direktive gibt an, dass Sie zum Abfragen des generierten **DataSet** [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] verwenden können. Diese Option wird verwendet, wenn auch die Option `/d` angegeben ist.  Weitere Informationen finden Sie unter [Abfragen von typisierten DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).  Die optionale `/n:`\-Direktive weist das Tool außerdem an, einen Namespace für das **DataSet** mit dem Namen **XSDSchema.Namespace** zu generieren.  Als Ergebnis dieses Befehls wird die Datei XSDSchemaFileName.cs ausgegeben, die kompiliert und in einer ADO.NET\-Anwendung verwendet werden kann.  Der generierte Code kann als Bibliothek oder Modul kompiliert werden.  
  
 Im folgenden Codebeispiel wird die Syntax dargestellt, die zum Kompilieren des generierten Codes als Bibliothek mithilfe des C\#\-Compilers \(csc.exe\) verwendet wird.  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 Die `/t:`\-Direktive weist das Tool an, eine Bibliothek zu kompilieren, und die `/r:`\-Direktiven geben die zum Kompilieren erforderlichen abhängigen Bibliotheken an.  Als Ergebnis des Befehls wird die Datei XSDSchemaFileName.dll ausgegeben, die an den Compiler übergeben werden kann, wenn eine ADO.NET\-Anwendung mit der `/r:`\-Direktive kompiliert wird.  
  
 Im folgenden Codebeispiel wird die Syntax für den Zugriff auf den Namespace dargestellt, der in einer ADO.NET\-Anwendung an XSD.exe übergeben wird.  
  
```vb  
Imports XSDSchema.Namespace  
  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 Im folgenden Codebeispiel wird ein typisiertes **DataSet** mit dem Namen **CustomerDataSet** verwendet, um eine Kundenliste aus der **Northwind**\-Datenbank zu laden.  Sobald die Daten mithilfe der **Fill** \-Methode geladen sind, werden im Beispiel alle Kunden in der Tabelle **Customers** mithilfe des typisierten **CustomersRow**\-Objekts \(**DataRow**\) durchlaufen.  Anders als durch die **DataColumnCollection** wird so ein direkter Zugriff auf die Spalte **CustomerID** bereitgestellt.  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 Im Folgenden wird das im Beispiel verwendete XML\-Schema dargestellt.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## Siehe auch  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataSet>   
 [Typisierte 'DataSets'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)