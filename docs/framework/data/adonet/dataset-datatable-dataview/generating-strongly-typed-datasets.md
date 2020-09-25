---
title: Generieren von stark typisierten "DataSets"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 1c65389c8c5664f86f3f0c04829a2422908d72d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202291"
---
# <a name="generating-strongly-typed-datasets"></a>Generieren von stark typisierten "DataSets"

Bei einem XML-Schema, das dem XSD-Standard (XML Schema Definition Language) entspricht, können Sie mit <xref:System.Data.DataSet> dem XSD.exe Tool, das mit dem Windows Software Development Kit (SDK) bereitgestellt wird, ein stark typisiertes generieren.  
  
 (Informationen zum Erstellen einer XSD aus Datenbanktabellen finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [Arbeiten mit Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).  
  
 Der folgende Code zeigt die Syntax zum Erstellen eines **DataSets** mithilfe dieses Tools.  
  
```console  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 In dieser Syntax weist die- `/d` Direktive das Tool an, ein **DataSet**zu generieren, und teilt dem Tool mit, `/l:` welche Sprache verwendet werden soll (z. b. c# oder Visual Basic .net). Die optionale- `/eld` Direktive gibt an, dass Sie LINQ to DataSet verwenden können, um das generierte **DataSet** abzufragen. Diese Option wird verwendet, wenn auch die Option `/d` angegeben ist. Weitere Informationen finden Sie unter [Abfragen von typisierten Datasets](../querying-typed-datasets.md). Die optionale- `/n:` Direktive weist das Tool an, auch einen Namespace für das **DataSet** mit dem Namen **xsdschema. Namespace**zu generieren. Als Ergebnis dieses Befehls wird die Datei XSDSchemaFileName.cs ausgegeben, die kompiliert und in einer ADO.NET-Anwendung verwendet werden kann. Der generierte Code kann als Bibliothek oder Modul kompiliert werden.  
  
 Im folgenden Codebeispiel wird die Syntax dargestellt, die zum Kompilieren des generierten Codes als Bibliothek mithilfe des C#-Compilers (csc.exe) verwendet wird.  
  
```console  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 Die `/t:`-Direktive weist das Tool an, eine Bibliothek zu kompilieren, und die `/r:`-Direktiven geben die zum Kompilieren erforderlichen abhängigen Bibliotheken an. Als Ergebnis des Befehls wird die Datei XSDSchemaFileName.dll ausgegeben, die an den Compiler übergeben werden kann, wenn eine ADO.NET-Anwendung mit der `/r:`-Anweisung kompiliert wird.  
  
 Im folgenden Codebeispiel wird die Syntax für den Zugriff auf den Namespace dargestellt, der in einer ADO.NET-Anwendung an XSD.exe übergeben wird.  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 Im folgenden Codebeispiel wird ein typisiertes **DataSet** mit dem Namen **CustomerDataSet** verwendet, um eine Liste der Kunden aus der **Northwind** -Datenbank zu laden. Sobald die Daten mithilfe der **Fill** -Methode geladen wurden, durchläuft das Beispiel die einzelnen Kunden in der Tabelle **Customers** mithilfe des typisierten **CustomersRow** -Objekts (**DataRow**). Dies ermöglicht den direkten Zugriff auf die Spalte " **CustomerID** " im Gegensatz zu " **DataColumnCollection**".  
  
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
  
 Im folgenden finden Sie das XML-Schema, das für das Beispiel verwendet wird:
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Typisierte "DataSets"](typed-datasets.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
