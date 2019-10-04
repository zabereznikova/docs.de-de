---
title: Generieren von stark typisierten "DataSets"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: ce7e5ad53f7aa5dad457ca1aa6ab76716086c0c3
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833994"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="8c718-102">Generieren von stark typisierten "DataSets"</span><span class="sxs-lookup"><span data-stu-id="8c718-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="8c718-103">Bei einem XML-Schema, das dem XSD-Standard (XML Schema Definition Language) entspricht, können Sie mit dem Tool XSD. exe, das mit dem Windows Software Development Kit (SDK) bereitgestellt wird, einen stark typisierten <xref:System.Data.DataSet> generieren.</span><span class="sxs-lookup"><span data-stu-id="8c718-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the Windows Software Development Kit (SDK).</span></span>  
  
 <span data-ttu-id="8c718-104">(Informationen zum Erstellen einer XSD aus Datenbanktabellen finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [Arbeiten mit Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span><span class="sxs-lookup"><span data-stu-id="8c718-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span></span>  
  
 <span data-ttu-id="8c718-105">Der folgende Code zeigt die Syntax zum Erstellen eines **DataSets** mithilfe dieses Tools.</span><span class="sxs-lookup"><span data-stu-id="8c718-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="8c718-106">In dieser Syntax weist die `/d`-Direktive das Tool an, ein **DataSet**zu generieren, und die `/l:` weist das Tool an, welche Sprache verwendet C# werden soll (z. b. oder Visual Basic .net).</span><span class="sxs-lookup"><span data-stu-id="8c718-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="8c718-107">Die optionale `/eld`-Direktive gibt an, dass Sie LINQ to DataSet verwenden können, um das generierte **DataSet** abzufragen.</span><span class="sxs-lookup"><span data-stu-id="8c718-107">The optional `/eld` directive specifies that you can use LINQ to DataSet to query against the generated **DataSet.**</span></span> <span data-ttu-id="8c718-108">Diese Option wird verwendet, wenn auch die Option `/d` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="8c718-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="8c718-109">Weitere Informationen finden Sie unter [Abfragen von typisierten Datasets](../querying-typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="8c718-109">For more information, see [Querying Typed DataSets](../querying-typed-datasets.md).</span></span> <span data-ttu-id="8c718-110">Die optionale `/n:`-Direktive weist das Tool an, auch einen Namespace für das **DataSet** mit dem Namen **xsdschema. Namespace**zu generieren.</span><span class="sxs-lookup"><span data-stu-id="8c718-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="8c718-111">Als Ergebnis dieses Befehls wird die Datei XSDSchemaFileName.cs ausgegeben, die kompiliert und in einer ADO.NET-Anwendung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8c718-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="8c718-112">Der generierte Code kann als Bibliothek oder Modul kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="8c718-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="8c718-113">Im folgenden Codebeispiel wird die Syntax dargestellt, die zum Kompilieren des generierten Codes als Bibliothek mithilfe des C#-Compilers (csc.exe) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8c718-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="8c718-114">Die `/t:`-Direktive weist das Tool an, eine Bibliothek zu kompilieren, und die `/r:`-Direktiven geben die zum Kompilieren erforderlichen abhängigen Bibliotheken an.</span><span class="sxs-lookup"><span data-stu-id="8c718-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="8c718-115">Als Ergebnis des Befehls wird die Datei XSDSchemaFileName.dll ausgegeben, die an den Compiler übergeben werden kann, wenn eine ADO.NET-Anwendung mit der `/r:`-Anweisung kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="8c718-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="8c718-116">Im folgenden Codebeispiel wird die Syntax für den Zugriff auf den Namespace dargestellt, der in einer ADO.NET-Anwendung an XSD.exe übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="8c718-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="8c718-117">Im folgenden Codebeispiel wird ein typisiertes **DataSet** mit dem Namen **CustomerDataSet** verwendet, um eine Liste der Kunden aus der **Northwind** -Datenbank zu laden.</span><span class="sxs-lookup"><span data-stu-id="8c718-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="8c718-118">Sobald die Daten mithilfe der **Fill** -Methode geladen wurden, durchläuft das Beispiel die einzelnen Kunden in der Tabelle **Customers** mithilfe des typisierten **CustomersRow** -Objekts (**DataRow**).</span><span class="sxs-lookup"><span data-stu-id="8c718-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="8c718-119">Dies ermöglicht den direkten Zugriff auf die Spalte " **CustomerID** " im Gegensatz zu " **DataColumnCollection**".</span><span class="sxs-lookup"><span data-stu-id="8c718-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
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
  
 <span data-ttu-id="8c718-120">Im folgenden finden Sie das XML-Schema, das für das Beispiel verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="8c718-120">The following is the XML Schema used for the example:</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c718-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c718-121">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="8c718-122">Typed DataSets (Typisierte DataSets)</span><span class="sxs-lookup"><span data-stu-id="8c718-122">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="8c718-123">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="8c718-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="8c718-124">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8c718-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
