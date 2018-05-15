---
title: Generieren von stark typisierten "DataSets"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 95bb536416a043fc392d0c4e94378239ae3ee37f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="719be-102">Generieren von stark typisierten "DataSets"</span><span class="sxs-lookup"><span data-stu-id="719be-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="719be-103">Bei einem XML-Schema, das dem XSD-Standard (XML Schema Definition Language) entspricht, können Sie mit dem Tool <legacyBold>XSD.exe</legacyBold>, das zusammen mit dem <xref:System.Data.DataSet> ausgeliefert wird, ein stark typisiertes [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)] generieren.</span><span class="sxs-lookup"><span data-stu-id="719be-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="719be-104">(Um XSD-Code aus Datenbanktabellen erstellen zu können, finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [arbeiten mit Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span><span class="sxs-lookup"><span data-stu-id="719be-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span></span>  
  
 <span data-ttu-id="719be-105">Der folgende Code zeigt die Syntax für das Generieren einer **DataSet** mit diesem Tool.</span><span class="sxs-lookup"><span data-stu-id="719be-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="719be-106">In dieser Syntax der `/d` -Direktive weist das Tool zum Generieren einer **DataSet**, und die `/l:` weist das Tool (z. B. c# oder Visual Basic .NET).) zu verwendende Programmiersprache an.</span><span class="sxs-lookup"><span data-stu-id="719be-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="719be-107">Das optionale `/eld` Richtlinie gibt an, dass Sie verwenden können, [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] um eine Abfrage für die generierte **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="719be-107">The optional `/eld` directive specifies that you can use [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] to query against the generated **DataSet.**</span></span> <span data-ttu-id="719be-108">Diese Option wird verwendet, wenn auch die Option `/d` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="719be-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="719be-109">Weitere Informationen finden Sie unter [Abfragen typisierter DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="719be-109">For more information, see [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="719be-110">Das optionale `/n:` -Direktive weist das Tool auch einen Namespace für generiert die **DataSet** aufgerufen **XSDSchema.Namespace**.</span><span class="sxs-lookup"><span data-stu-id="719be-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="719be-111">Als Ergebnis dieses Befehls wird die Datei XSDSchemaFileName.cs ausgegeben, die kompiliert und in einer ADO.NET-Anwendung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="719be-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="719be-112">Der generierte Code kann als Bibliothek oder Modul kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="719be-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="719be-113">Im folgenden Codebeispiel wird die Syntax dargestellt, die zum Kompilieren des generierten Codes als Bibliothek mithilfe des C#-Compilers (csc.exe) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="719be-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="719be-114">Die `/t:`-Direktive weist das Tool an, eine Bibliothek zu kompilieren, und die `/r:`-Direktiven geben die zum Kompilieren erforderlichen abhängigen Bibliotheken an.</span><span class="sxs-lookup"><span data-stu-id="719be-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="719be-115">Als Ergebnis des Befehls wird die Datei XSDSchemaFileName.dll ausgegeben, die an den Compiler übergeben werden kann, wenn eine ADO.NET-Anwendung mit der `/r:`-Direktive kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="719be-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="719be-116">Im folgenden Codebeispiel wird die Syntax für den Zugriff auf den Namespace dargestellt, der in einer ADO.NET-Anwendung an XSD.exe übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="719be-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="719be-117">Im folgenden Codebeispiel wird ein typisiertes **DataSet** mit dem Namen **CustomerDataSet** beim Laden der einer Liste von Kunden aus der **Northwind** Datenbank.</span><span class="sxs-lookup"><span data-stu-id="719be-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="719be-118">Sobald die Daten geladen werden mithilfe der **füllen** -Methode, im Beispiel in einer Schleife durchlaufen alle Kunden in der **Kunden** Tabelle mithilfe des typisierten **CustomersRow** ( **DataRow**) Objekt.</span><span class="sxs-lookup"><span data-stu-id="719be-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="719be-119">Dies bietet direkten Zugriff auf die **CustomerID** Spalte, als durch die **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="719be-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
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
  
 <span data-ttu-id="719be-120">Im Folgenden wird das im Beispiel verwendete XML-Schema dargestellt.</span><span class="sxs-lookup"><span data-stu-id="719be-120">Following is the XML Schema used for the example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="719be-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="719be-121">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="719be-122">Typed DataSets (Typisierte DataSets)</span><span class="sxs-lookup"><span data-stu-id="719be-122">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="719be-123">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="719be-123">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="719be-124">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="719be-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
