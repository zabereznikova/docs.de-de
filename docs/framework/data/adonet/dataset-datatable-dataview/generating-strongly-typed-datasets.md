---
title: Generieren von stark typisierten "DataSets"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 867c6f5fa918b0886d8d618e89c62201cd92b213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="generating-strongly-typed-datasets"></a>Generieren von stark typisierten "DataSets"
Bei einem XML-Schema, das dem XSD-Standard (XML Schema Definition Language) entspricht, können Sie mit dem Tool <legacyBold>XSD.exe</legacyBold>, das zusammen mit dem <xref:System.Data.DataSet> ausgeliefert wird, ein stark typisiertes [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)] generieren.  
  
 (Um XSD-Code aus Datenbanktabellen erstellen zu können, finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [arbeiten mit Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).  
  
 Der folgende Code zeigt die Syntax für das Generieren einer **DataSet** mit diesem Tool.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 In dieser Syntax der `/d` -Direktive weist das Tool zum Generieren einer **DataSet**, und die `/l:` weist das Tool (z. B. c# oder Visual Basic .NET).) zu verwendende Programmiersprache an. Das optionale `/eld` Richtlinie gibt an, dass Sie verwenden können, [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] um eine Abfrage für die generierte **DataSet.** Diese Option wird verwendet, wenn auch die Option `/d` angegeben ist. Weitere Informationen finden Sie unter [Abfragen typisierter DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md). Das optionale `/n:` -Direktive weist das Tool auch einen Namespace für generiert die **DataSet** aufgerufen **XSDSchema.Namespace**. Als Ergebnis dieses Befehls wird die Datei XSDSchemaFileName.cs ausgegeben, die kompiliert und in einer ADO.NET-Anwendung verwendet werden kann. Der generierte Code kann als Bibliothek oder Modul kompiliert werden.  
  
 Im folgenden Codebeispiel wird die Syntax dargestellt, die zum Kompilieren des generierten Codes als Bibliothek mithilfe des C#-Compilers (csc.exe) verwendet wird.  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 Die `/t:`-Direktive weist das Tool an, eine Bibliothek zu kompilieren, und die `/r:`-Direktiven geben die zum Kompilieren erforderlichen abhängigen Bibliotheken an. Als Ergebnis des Befehls wird die Datei XSDSchemaFileName.dll ausgegeben, die an den Compiler übergeben werden kann, wenn eine ADO.NET-Anwendung mit der `/r:`-Direktive kompiliert wird.  
  
 Im folgenden Codebeispiel wird die Syntax für den Zugriff auf den Namespace dargestellt, der in einer ADO.NET-Anwendung an XSD.exe übergeben wird.  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 Im folgenden Codebeispiel wird ein typisiertes **DataSet** mit dem Namen **CustomerDataSet** beim Laden der einer Liste von Kunden aus der **Northwind** Datenbank. Sobald die Daten geladen werden mithilfe der **füllen** -Methode, im Beispiel in einer Schleife durchlaufen alle Kunden in der **Kunden** Tabelle mithilfe des typisierten **CustomersRow** ( **DataRow**) Objekt. Dies bietet direkten Zugriff auf die **CustomerID** Spalte, als durch die **DataColumnCollection**.  
  
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
  
 Im Folgenden wird das im Beispiel verwendete XML-Schema dargestellt.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [Typed DataSets (Typisierte DataSets)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
