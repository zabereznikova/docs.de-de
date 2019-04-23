---
title: Generieren von stark typisierten "DataSets"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 25883b7be10c68e527e4e04182b7162574b994d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149629"
---
# <a name="generating-strongly-typed-datasets"></a>Generieren von stark typisierten "DataSets"
Bei einem XML-Schema, das dem XSD-Standard (XML Schema Definition Language) entspricht, können Sie mit dem Tool <legacyBold>XSD.exe</legacyBold>, das zusammen mit dem <xref:System.Data.DataSet> ausgeliefert wird, ein stark typisiertes [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)] generieren.  
  
 (Um ein XSD-Schema aus Datenbanktabellen erstellen zu können, finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [arbeiten mit Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).  
  
 Der folgende Code zeigt die Syntax für das Generieren einer **DataSet** mit diesem Tool.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 In dieser Syntax der `/d` -Anweisung weist das Tool zum Generieren einer **DataSet**, und die `/l:` weist das Tool zu (z. B. c# oder Visual Basic .NET) zu verwendende Sprache. Der optionale `/eld` Richtlinie gibt an, dass Sie verwenden können, [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] zum Abfragen des generierten **DataSet.** Diese Option wird verwendet, wenn auch die Option `/d` angegeben ist. Weitere Informationen finden Sie unter [Abfragen typisierter DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md). Das optionale `/n:` -Anweisung weist das Tool auch generieren, einen Namespace für die **DataSet** namens **XSDSchema.Namespace**. Als Ergebnis dieses Befehls wird die Datei XSDSchemaFileName.cs ausgegeben, die kompiliert und in einer ADO.NET-Anwendung verwendet werden kann. Der generierte Code kann als Bibliothek oder Modul kompiliert werden.  
  
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
  
 Im folgenden Codebeispiel wird ein typisiertes **DataSet** mit dem Namen **CustomerDataSet** beim Laden der einer Liste von Kunden aus der **Northwind** Datenbank. Nach dem Laden der Daten mithilfe der **füllen** -Methode, im Beispiel führt eine Schleife durch alle Kunden in den **Kunden** Tabelle mithilfe des typisierten **CustomersRow** ( **DataRow**) Objekt. Dies bietet direkten Zugriff auf die **"CustomerID"** Spalte, als durch die **DataColumnCollection**.  
  
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

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Typed DataSets (Typisierte DataSets)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
