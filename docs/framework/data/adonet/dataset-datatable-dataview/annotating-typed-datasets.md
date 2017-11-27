---
title: "Hinzufügen von Anmerkungen zu typisierten \"DataSets\""
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
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d3965ced44bae21feef3d01d49149387fce4fa46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="annotating-typed-datasets"></a><span data-ttu-id="386b4-102">Hinzufügen von Anmerkungen zu typisierten "DataSets"</span><span class="sxs-lookup"><span data-stu-id="386b4-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="386b4-103">Anmerkungen ermöglichen Ihnen die Namensänderung von Elementen in einem typisierten <xref:System.Data.DataSet>, ohne das zugrunde liegende Schema ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="386b4-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="386b4-104">Die Namen der Elemente im zugrunde liegenden Schema ändern würde das typisierte **DataSet** zum Verweisen auf Objekte, die nicht in der Datenquelle vorhanden sind, als auch verlieren einen Verweis auf die Objekte, die in der Datenquelle vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="386b4-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="386b4-105">Verwenden von Anmerkungen, können Sie die Namen von Objekten im typisierten anpassen **DataSet** in aussagekräftigere Namen ausführenden Code besser lesbar und Ihre typisierte **DataSet** einfacher für Clients verwenden, lassen zugrunde liegende Schema intakt.</span><span class="sxs-lookup"><span data-stu-id="386b4-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="386b4-106">Z. B. das folgende Schemaelement für die **Kunden** Tabelle mit den **Northwind** Datenbank würde eine **DataRow** Objektname des  **CustomersRow** und ein <xref:System.Data.DataRowCollection> mit dem Namen **Kunden**.</span><span class="sxs-lookup"><span data-stu-id="386b4-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="386b4-107">Ein **DataRowCollection** Name des **Kunden** ist sinnvoll, im Clientcode, aber ein **DataRow** Name des **CustomersRow** ist irreführend Da es sich um ein einzelnes Objekt handelt.</span><span class="sxs-lookup"><span data-stu-id="386b4-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="386b4-108">Darüber hinaus gemeinsam Szenarios, das Objekt verwiesen ohne die **Zeile** Bezeichner und stattdessen würde er einfach als bezeichnet eine **Kunden** Objekt.</span><span class="sxs-lookup"><span data-stu-id="386b4-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="386b4-109">Die Lösung besteht darin, kommentieren das Schema und neue Namen für die **DataRow** und **DataRowCollection** Objekte.</span><span class="sxs-lookup"><span data-stu-id="386b4-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="386b4-110">Der folgende Code zeigt das vorhergehende Schema mit Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="386b4-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="386b4-111">Angeben einer **TypedName** Wert **Kunden** führt zu einer **DataRow** Objektname des **Kunden**.</span><span class="sxs-lookup"><span data-stu-id="386b4-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="386b4-112">Angeben einer **TypedPlural** Wert **Kunden** behält die **DataRowCollection** Name des **Kunden**.</span><span class="sxs-lookup"><span data-stu-id="386b4-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="386b4-113">In der folgenden Tabelle sind die möglichen Anmerkungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="386b4-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="386b4-114">Anmerkung</span><span class="sxs-lookup"><span data-stu-id="386b4-114">Annotation</span></span>|<span data-ttu-id="386b4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="386b4-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="386b4-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="386b4-116">**typedName**</span></span>|<span data-ttu-id="386b4-117">Name des Objekts.</span><span class="sxs-lookup"><span data-stu-id="386b4-117">Name of the object.</span></span>|  
|<span data-ttu-id="386b4-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="386b4-118">**typedPlural**</span></span>|<span data-ttu-id="386b4-119">Name einer Auflistung von Objekten.</span><span class="sxs-lookup"><span data-stu-id="386b4-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="386b4-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="386b4-120">**typedParent**</span></span>|<span data-ttu-id="386b4-121">Name des Objekts, wenn in einer übergeordneten Beziehung darauf verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="386b4-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="386b4-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="386b4-122">**typedChildren**</span></span>|<span data-ttu-id="386b4-123">Name der Methode zum Zurückgeben von Objekten aus einer untergeordneten Beziehung.</span><span class="sxs-lookup"><span data-stu-id="386b4-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="386b4-124">**nullValue**</span><span class="sxs-lookup"><span data-stu-id="386b4-124">**nullValue**</span></span>|<span data-ttu-id="386b4-125">Wenn die zugrunde liegenden Wert ist **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="386b4-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="386b4-126">Finden Sie in der folgenden Tabelle **NullValue** Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="386b4-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="386b4-127">Die Standardeinstellung ist **_throw**.</span><span class="sxs-lookup"><span data-stu-id="386b4-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="386b4-128">Die folgende Tabelle zeigt die Werte, die für angegeben werden, können die **NullValue** Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="386b4-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="386b4-129">nullValue-Wert</span><span class="sxs-lookup"><span data-stu-id="386b4-129">nullValue Value</span></span>|<span data-ttu-id="386b4-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="386b4-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="386b4-131">*Ersatzwert*</span><span class="sxs-lookup"><span data-stu-id="386b4-131">*Replacement Value*</span></span>|<span data-ttu-id="386b4-132">Gibt einen Wert an, der zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="386b4-132">Specify a value to be returned.</span></span> <span data-ttu-id="386b4-133">Der zurückgegebene Wert muss mit dem Elementtyp übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="386b4-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="386b4-134">Verwenden Sie z. B. `nullValue="0"`, um 0 für NULL-Ganzzahlfelder zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="386b4-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="386b4-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="386b4-135">**_throw**</span></span>|<span data-ttu-id="386b4-136">Löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="386b4-136">Throw an exception.</span></span> <span data-ttu-id="386b4-137">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="386b4-137">This is the default.</span></span>|  
|<span data-ttu-id="386b4-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="386b4-138">**_null**</span></span>|<span data-ttu-id="386b4-139">Gibt einen NULL-Verweis aus oder löst eine Ausnahme aus, wenn ein primitiver Typ festgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="386b4-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="386b4-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="386b4-140">**_empty**</span></span>|<span data-ttu-id="386b4-141">Für Zeichenfolgen wird zurückgeben **"String.Empty"**, andernfalls wird ein Objekt aus einem leeren Konstruktor erstellt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="386b4-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="386b4-142">Wenn ein primitiver Typ festgestellt wird, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="386b4-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="386b4-143">Die folgende Tabelle zeigt die Standardwerte für Objekte in einem typisierten **DataSet** und die verfügbaren Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="386b4-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="386b4-144">Objekt/Methode/Ereignis</span><span class="sxs-lookup"><span data-stu-id="386b4-144">Object/Method/Event</span></span>|<span data-ttu-id="386b4-145">Standard</span><span class="sxs-lookup"><span data-stu-id="386b4-145">Default</span></span>|<span data-ttu-id="386b4-146">Anmerkung</span><span class="sxs-lookup"><span data-stu-id="386b4-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="386b4-147">**DataTable**</span><span class="sxs-lookup"><span data-stu-id="386b4-147">**DataTable**</span></span>|<span data-ttu-id="386b4-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="386b4-148">TableNameDataTable</span></span>|<span data-ttu-id="386b4-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="386b4-149">typedPlural</span></span>|  
|<span data-ttu-id="386b4-150">**DataTable** Methoden</span><span class="sxs-lookup"><span data-stu-id="386b4-150">**DataTable** Methods</span></span>|<span data-ttu-id="386b4-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="386b4-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="386b4-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="386b4-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="386b4-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="386b4-153">DeleteTableNameRow</span></span>|<span data-ttu-id="386b4-154">typedName</span><span class="sxs-lookup"><span data-stu-id="386b4-154">typedName</span></span>|  
|<span data-ttu-id="386b4-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="386b4-155">**DataRowCollection**</span></span>|<span data-ttu-id="386b4-156">TableName</span><span class="sxs-lookup"><span data-stu-id="386b4-156">TableName</span></span>|<span data-ttu-id="386b4-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="386b4-157">typedPlural</span></span>|  
|<span data-ttu-id="386b4-158">**DataRow**</span><span class="sxs-lookup"><span data-stu-id="386b4-158">**DataRow**</span></span>|<span data-ttu-id="386b4-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="386b4-159">TableNameRow</span></span>|<span data-ttu-id="386b4-160">typedName</span><span class="sxs-lookup"><span data-stu-id="386b4-160">typedName</span></span>|  
|<span data-ttu-id="386b4-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="386b4-161">**DataColumn**</span></span>|<span data-ttu-id="386b4-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="386b4-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="386b4-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="386b4-163">DataRow.ColumnName</span></span>|<span data-ttu-id="386b4-164">typedName</span><span class="sxs-lookup"><span data-stu-id="386b4-164">typedName</span></span>|  
|<span data-ttu-id="386b4-165">**Property**</span><span class="sxs-lookup"><span data-stu-id="386b4-165">**Property**</span></span>|<span data-ttu-id="386b4-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="386b4-166">PropertyName</span></span>|<span data-ttu-id="386b4-167">typedName</span><span class="sxs-lookup"><span data-stu-id="386b4-167">typedName</span></span>|  
|<span data-ttu-id="386b4-168">**Untergeordnete** Zugriffsmethode</span><span class="sxs-lookup"><span data-stu-id="386b4-168">**Child** Accessor</span></span>|<span data-ttu-id="386b4-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="386b4-169">GetChildTableNameRows</span></span>|<span data-ttu-id="386b4-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="386b4-170">typedChildren</span></span>|  
|<span data-ttu-id="386b4-171">**Übergeordnete** Zugriffsmethode</span><span class="sxs-lookup"><span data-stu-id="386b4-171">**Parent** Accessor</span></span>|<span data-ttu-id="386b4-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="386b4-172">TableNameRow</span></span>|<span data-ttu-id="386b4-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="386b4-173">typedParent</span></span>|  
|<span data-ttu-id="386b4-174">**DataSet** Ereignisse</span><span class="sxs-lookup"><span data-stu-id="386b4-174">**DataSet** Events</span></span>|<span data-ttu-id="386b4-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="386b4-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="386b4-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="386b4-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="386b4-177">typedName</span><span class="sxs-lookup"><span data-stu-id="386b4-177">typedName</span></span>|  
  
 <span data-ttu-id="386b4-178">Um typisierte **DataSet** Anmerkungen, müssen Sie die folgenden einschließen **Xmlns** Verweis in Ihrem Schema für XML Schema Definition Language (XSD).</span><span class="sxs-lookup"><span data-stu-id="386b4-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="386b4-179">(Um XSD-Code aus Datenbanktabellen erstellen zu können, finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [arbeiten mit Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span><span class="sxs-lookup"><span data-stu-id="386b4-179">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span></span>  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="386b4-180">Folgender Ausdruck ist ein Beispielschema mit Anmerkungen, die verfügbar macht die **Kunden** Tabelle mit der **Northwind** Datenbank mit einer Beziehung zur der **Aufträge** Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="386b4-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"   
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""   
      xmlns:xs="http://www.w3.org/2001/XMLSchema"   
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone" codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order" codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"                  codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"   
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter" codegen:nullValue="1980-01-01T00:00:00"   
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="386b4-181">Das folgende Codebeispiel verwendet eine stark typisierte **DataSet** aus dem Beispielschema erstellt.</span><span class="sxs-lookup"><span data-stu-id="386b4-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="386b4-182">Es verwendet einen <xref:System.Data.SqlClient.SqlDataAdapter> zum Auffüllen der **Kunden** Tabelle und ein anderes <xref:System.Data.SqlClient.SqlDataAdapter> zum Auffüllen der **Aufträge** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="386b4-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="386b4-183">Das stark typisierte **DataSet** definiert die **von "DataRelations"**.</span><span class="sxs-lookup"><span data-stu-id="386b4-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomeromer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",   
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new   
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =   
    customers.Customers.NewCustomeromer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="386b4-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="386b4-184">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="386b4-185">Typed DataSets (Typisierte DataSets)</span><span class="sxs-lookup"><span data-stu-id="386b4-185">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="386b4-186">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="386b4-186">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="386b4-187">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="386b4-187">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
