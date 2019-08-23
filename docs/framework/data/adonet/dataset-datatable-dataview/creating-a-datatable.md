---
title: Erstellen einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: b56d2f8cd46f3184f1001c8bd6a70dbfc4968968
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937027"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="9eef9-102">Erstellen einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="9eef9-102">Creating a DataTable</span></span>
<span data-ttu-id="9eef9-103">Eine <xref:System.Data.DataTable>, die eine Tabelle mit relationalen Daten im Speicher darstellt, kann erstellt und unabhängig verwendet werden. Oder sie kann von anderen .NET Framework-Objekten, am häufigsten als Member von einem <xref:System.Data.DataSet>, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9eef9-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="9eef9-104">Sie können ein **Daten** Objekt mit dem entsprechenden **Daten** tabellenkonstruktor erstellen.</span><span class="sxs-lookup"><span data-stu-id="9eef9-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="9eef9-105">Sie können es dem **DataSet** hinzufügen, indem Sie die **Add** -Methode verwenden, um es der Tables- **Auflistung** des **datables** -Objekts hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9eef9-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="9eef9-106">Sie können mithilfe der **Fill** -Methode oder der **FillSchema** -Methode des **DataAdapter** -Objekts oder aus einem vordefinierten oder abgelegten XML-Schema mithilfe von "read **XML**" und "Read XmlSchema" auch **Daten** in einem **DataSet** erstellen.oder **InferXmlSchema** -Methoden des **DataSets**.</span><span class="sxs-lookup"><span data-stu-id="9eef9-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="9eef9-107">Beachten Sie, dass Sie, nachdem Sie eine Datentabelle als Member der **Tables** -Auflistung eines **DataSets**hinzugefügt haben, Sie nicht zur **Auflistung** von Tabellen eines beliebigen anderen **DataSets**hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="9eef9-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="9eef9-108">Wenn Sie erstmalig eine **Daten**Tabelle erstellen, hat Sie kein Schema (d. h. eine Struktur).</span><span class="sxs-lookup"><span data-stu-id="9eef9-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="9eef9-109">Um das Schema der Tabelle zu definieren, müssen Sie-Objekte erstellen <xref:System.Data.DataColumn> und der **Columns** -Auflistung der Tabelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9eef9-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="9eef9-110">Sie können auch eine Primärschlüssel Spalte für die Tabelle definieren und Einschränkungs Objekte erstellen und der Einschränkungs Auflistung der Tabelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9eef9-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="9eef9-111">Nachdem Sie das Schema für eine **Daten**Tabelle definiert haben, können Sie der Tabelle Daten Zeilen hinzufügen, indem Sie der **Rows** -Auflistung der Tabelle **DataRow** -Objekte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9eef9-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="9eef9-112">Sie müssen keinen Wert für die <xref:System.Data.DataTable.TableName%2A> -Eigenschaft angeben, wenn Sie eine **Daten**Tabelle erstellen. Sie können die Eigenschaft zu einem anderen Zeitpunkt angeben, oder Sie können Sie leer lassen.</span><span class="sxs-lookup"><span data-stu-id="9eef9-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="9eef9-113">Wenn Sie jedoch eine Tabelle ohne **TableName** -Wert zu einem **DataSet**hinzufügen, erhält die Tabelle einen inkrementellen Standardnamen der Tabelle*N*, beginnend mit "Table" für Table0.</span><span class="sxs-lookup"><span data-stu-id="9eef9-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9eef9-114">Es wird empfohlen, dass Sie die Benennungs Konvention "Table*N*" vermeiden, wenn Sie einen **TableName** -Wert angeben, da der von Ihnen bereitgestellte Name möglicherweise mit einem vorhandenen Standard Tabellennamen im **DataSet**in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="9eef9-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="9eef9-115">Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9eef9-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="9eef9-116">Im folgenden Beispiel wird eine Instanz eines **Daten** Tabelle-Objekts erstellt und dem Namen "Customers" zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9eef9-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="9eef9-117">Im folgenden Beispiel wird eine Instanz einer Datentabelle erstellt, indem Sie der **Tables** - **Auflistung** eines **DataSets**hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="9eef9-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="9eef9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9eef9-118">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [<span data-ttu-id="9eef9-119">DataTables</span><span class="sxs-lookup"><span data-stu-id="9eef9-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="9eef9-120">Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)</span><span class="sxs-lookup"><span data-stu-id="9eef9-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="9eef9-121">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="9eef9-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="9eef9-122">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="9eef9-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="9eef9-123">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="9eef9-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
