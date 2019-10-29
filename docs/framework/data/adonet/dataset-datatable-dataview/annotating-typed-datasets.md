---
title: Hinzufügen von Anmerkungen zu typisierten "DataSets"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: df6da84dfc120e3f6c3cb0e46729ca2cecc9fe3a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040401"
---
# <a name="annotating-typed-datasets"></a><span data-ttu-id="7e564-102">Hinzufügen von Anmerkungen zu typisierten "DataSets"</span><span class="sxs-lookup"><span data-stu-id="7e564-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="7e564-103">Anmerkungen ermöglichen Ihnen die Namensänderung von Elementen in einem typisierten <xref:System.Data.DataSet>, ohne das zugrunde liegende Schema ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7e564-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="7e564-104">Wenn Sie die Namen der Elemente im zugrunde liegenden Schema ändern, verweist das typisierte **DataSet** auf Objekte, die in der Datenquelle nicht vorhanden sind, und Sie verlieren einen Verweis auf die Objekte, die in der Datenquelle vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7e564-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="7e564-105">Mit Anmerkungen können Sie die Namen von Objekten in Ihrem typisierten **DataSet** mit aussagekräftigeren Namen anpassen, sodass der Code besser lesbar ist und das typisierte **DataSet** für Clients einfacher zu verwenden ist, während das zugrunde liegende Schema intakt bleibt.</span><span class="sxs-lookup"><span data-stu-id="7e564-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="7e564-106">Das folgende Schema Element für die **Customers** -Tabelle der **Northwind** -Datenbank würde z. b. den Namen des **DataRow** -Objekts **CustomersRow** und eine <xref:System.Data.DataRowCollection> mit dem Namen **Customers**ergeben.</span><span class="sxs-lookup"><span data-stu-id="7e564-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="7e564-107">Der **DataRowCollection** -Name von **Kunden** ist im Client Code aussagekräftig, aber der **DataRow** -Name **CustomersRow** ist irreführend, da es sich um ein einzelnes Objekt handelt.</span><span class="sxs-lookup"><span data-stu-id="7e564-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="7e564-108">In gängigen Szenarien wird das Objekt auch ohne den **Zeilen** Bezeichner referenziert und stattdessen einfach als **Customer** -Objekt bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7e564-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="7e564-109">Die Lösung besteht darin, das Schema mit Anmerkungen zu versehen und neue Namen für die Objekte **DataRow** und **DataRowCollection** zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="7e564-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="7e564-110">Der folgende Code zeigt das vorhergehende Schema mit Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="7e564-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="7e564-111">Das Angeben eines **typedName** -Werts von **Customer** führt zu einem **DataRow** -Objektnamen von **Customer**.</span><span class="sxs-lookup"><span data-stu-id="7e564-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="7e564-112">Wenn Sie einen **typedPlural** -Wert von **Kunden** angeben, wird der **DataRowCollection** -Name von **Kunden**beibehalten.</span><span class="sxs-lookup"><span data-stu-id="7e564-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="7e564-113">In der folgenden Tabelle sind die möglichen Anmerkungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7e564-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="7e564-114">Anmerkung</span><span class="sxs-lookup"><span data-stu-id="7e564-114">Annotation</span></span>|<span data-ttu-id="7e564-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e564-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="7e564-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="7e564-116">**typedName**</span></span>|<span data-ttu-id="7e564-117">Name des Objekts.</span><span class="sxs-lookup"><span data-stu-id="7e564-117">Name of the object.</span></span>|  
|<span data-ttu-id="7e564-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="7e564-118">**typedPlural**</span></span>|<span data-ttu-id="7e564-119">Name einer Auflistung von Objekten.</span><span class="sxs-lookup"><span data-stu-id="7e564-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="7e564-120">**typedparent**</span><span class="sxs-lookup"><span data-stu-id="7e564-120">**typedParent**</span></span>|<span data-ttu-id="7e564-121">Name des Objekts, wenn in einer übergeordneten Beziehung darauf verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7e564-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="7e564-122">**typedchildren**</span><span class="sxs-lookup"><span data-stu-id="7e564-122">**typedChildren**</span></span>|<span data-ttu-id="7e564-123">Name der Methode zum Zurückgeben von Objekten aus einer untergeordneten Beziehung.</span><span class="sxs-lookup"><span data-stu-id="7e564-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="7e564-124">**NullValue**</span><span class="sxs-lookup"><span data-stu-id="7e564-124">**nullValue**</span></span>|<span data-ttu-id="7e564-125">Wert, wenn der zugrunde liegende Wert **DBNull**ist.</span><span class="sxs-lookup"><span data-stu-id="7e564-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="7e564-126">In der folgenden Tabelle finden Sie Informationen zu **NullValue** -Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="7e564-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="7e564-127">Der Standardwert ist **_throw**.</span><span class="sxs-lookup"><span data-stu-id="7e564-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="7e564-128">In der folgenden Tabelle sind die Werte aufgeführt, die für die **NullValue** -Anmerkung angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="7e564-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="7e564-129">nullValue-Wert</span><span class="sxs-lookup"><span data-stu-id="7e564-129">nullValue Value</span></span>|<span data-ttu-id="7e564-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e564-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="7e564-131">*Ersatzwert*</span><span class="sxs-lookup"><span data-stu-id="7e564-131">*Replacement Value*</span></span>|<span data-ttu-id="7e564-132">Gibt einen Wert an, der zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e564-132">Specify a value to be returned.</span></span> <span data-ttu-id="7e564-133">Der zurückgegebene Wert muss mit dem Elementtyp übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="7e564-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="7e564-134">Verwenden Sie z. B. `nullValue="0"`, um 0 für NULL-Ganzzahlfelder zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="7e564-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="7e564-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="7e564-135">**_throw**</span></span>|<span data-ttu-id="7e564-136">Löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="7e564-136">Throw an exception.</span></span> <span data-ttu-id="7e564-137">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7e564-137">This is the default.</span></span>|  
|<span data-ttu-id="7e564-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="7e564-138">**_null**</span></span>|<span data-ttu-id="7e564-139">Gibt einen NULL-Verweis aus oder löst eine Ausnahme aus, wenn ein primitiver Typ festgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7e564-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="7e564-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="7e564-140">**_empty**</span></span>|<span data-ttu-id="7e564-141">Für Zeichen folgen wird **String. Empty**zurückgegeben, andernfalls wird ein Objekt zurückgegeben, das aus einem leeren Konstruktor erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7e564-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="7e564-142">Wenn ein primitiver Typ festgestellt wird, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7e564-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="7e564-143">In der folgenden Tabelle werden die Standardwerte für Objekte in einem typisierten **DataSet** und die verfügbaren Anmerkungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e564-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="7e564-144">Objekt/Methode/Ereignis</span><span class="sxs-lookup"><span data-stu-id="7e564-144">Object/Method/Event</span></span>|<span data-ttu-id="7e564-145">Default</span><span class="sxs-lookup"><span data-stu-id="7e564-145">Default</span></span>|<span data-ttu-id="7e564-146">Anmerkung</span><span class="sxs-lookup"><span data-stu-id="7e564-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="7e564-147">**DataTable**</span><span class="sxs-lookup"><span data-stu-id="7e564-147">**DataTable**</span></span>|<span data-ttu-id="7e564-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="7e564-148">TableNameDataTable</span></span>|<span data-ttu-id="7e564-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="7e564-149">typedPlural</span></span>|  
|<span data-ttu-id="7e564-150">**Daten** Tabelle Anzuwenden</span><span class="sxs-lookup"><span data-stu-id="7e564-150">**DataTable** Methods</span></span>|<span data-ttu-id="7e564-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="7e564-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="7e564-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="7e564-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="7e564-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="7e564-153">DeleteTableNameRow</span></span>|<span data-ttu-id="7e564-154">typedName</span><span class="sxs-lookup"><span data-stu-id="7e564-154">typedName</span></span>|  
|<span data-ttu-id="7e564-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="7e564-155">**DataRowCollection**</span></span>|<span data-ttu-id="7e564-156">TableName</span><span class="sxs-lookup"><span data-stu-id="7e564-156">TableName</span></span>|<span data-ttu-id="7e564-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="7e564-157">typedPlural</span></span>|  
|<span data-ttu-id="7e564-158">**DataRow**</span><span class="sxs-lookup"><span data-stu-id="7e564-158">**DataRow**</span></span>|<span data-ttu-id="7e564-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="7e564-159">TableNameRow</span></span>|<span data-ttu-id="7e564-160">typedName</span><span class="sxs-lookup"><span data-stu-id="7e564-160">typedName</span></span>|  
|<span data-ttu-id="7e564-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="7e564-161">**DataColumn**</span></span>|<span data-ttu-id="7e564-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="7e564-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="7e564-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="7e564-163">DataRow.ColumnName</span></span>|<span data-ttu-id="7e564-164">typedName</span><span class="sxs-lookup"><span data-stu-id="7e564-164">typedName</span></span>|  
|<span data-ttu-id="7e564-165">**Property**</span><span class="sxs-lookup"><span data-stu-id="7e564-165">**Property**</span></span>|<span data-ttu-id="7e564-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="7e564-166">PropertyName</span></span>|<span data-ttu-id="7e564-167">typedName</span><span class="sxs-lookup"><span data-stu-id="7e564-167">typedName</span></span>|  
|<span data-ttu-id="7e564-168">Untergeordnetes Element Accessor</span><span class="sxs-lookup"><span data-stu-id="7e564-168">**Child** Accessor</span></span>|<span data-ttu-id="7e564-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="7e564-169">GetChildTableNameRows</span></span>|<span data-ttu-id="7e564-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="7e564-170">typedChildren</span></span>|  
|<span data-ttu-id="7e564-171">Über **geordnetes** Element Accessor</span><span class="sxs-lookup"><span data-stu-id="7e564-171">**Parent** Accessor</span></span>|<span data-ttu-id="7e564-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="7e564-172">TableNameRow</span></span>|<span data-ttu-id="7e564-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="7e564-173">typedParent</span></span>|  
|<span data-ttu-id="7e564-174">**DataSet** Fall</span><span class="sxs-lookup"><span data-stu-id="7e564-174">**DataSet** Events</span></span>|<span data-ttu-id="7e564-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="7e564-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="7e564-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="7e564-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="7e564-177">typedName</span><span class="sxs-lookup"><span data-stu-id="7e564-177">typedName</span></span>|  
  
 <span data-ttu-id="7e564-178">Um typisierte **datasetanmerkungen** verwenden zu können, müssen Sie den folgenden **xmlns** -Verweis in das XSD-Schema (XML Schema Definition Language) einschließen.</span><span class="sxs-lookup"><span data-stu-id="7e564-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="7e564-179">Informationen zum Erstellen einer XSD aus Datenbanktabellen finden Sie unter <xref:System.Data.DataSet.WriteXmlSchema%2A> oder [Arbeiten mit Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="7e564-179">To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span></span>  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="7e564-180">Das folgende Beispiel zeigt ein Schema mit Anmerkungen, das die **Customers** -Tabelle der **Northwind** -Datenbank mit einer Beziehung zur Tabelle **Orders** verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="7e564-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
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
  
 <span data-ttu-id="7e564-181">Im folgenden Codebeispiel wird ein stark typisiertes **DataSet** verwendet, das aus dem Beispiel Schema erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7e564-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="7e564-182">Er verwendet eine <xref:System.Data.SqlClient.SqlDataAdapter>, um die Tabelle **Customers** aufzufüllen, und eine weitere <xref:System.Data.SqlClient.SqlDataAdapter>, um die Tabelle **Orders** aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="7e564-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="7e564-183">Das **DataSet** mit starker Typisierung definiert die **DataRelations**.</span><span class="sxs-lookup"><span data-stu-id="7e564-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
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
    customers.Customers.NewCustomer()  
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
    customers.Customers.NewCustomer();  
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
  
## <a name="see-also"></a><span data-ttu-id="7e564-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e564-184">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="7e564-185">Typed DataSets (Typisierte DataSets)</span><span class="sxs-lookup"><span data-stu-id="7e564-185">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="7e564-186">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="7e564-186">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="7e564-187">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7e564-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
