---
title: Erstellen einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: ad3f8bc6b42c5a54b42100a5d010e097ba80adc2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521132"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="8ee38-102">Erstellen einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="8ee38-102">Creating a DataTable</span></span>
<span data-ttu-id="8ee38-103">Eine <xref:System.Data.DataTable>, die eine Tabelle mit relationalen Daten im Speicher darstellt, kann erstellt und unabhängig verwendet werden. Oder sie kann von anderen .NET Framework-Objekten, am häufigsten als Member von einem <xref:System.Data.DataSet>, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ee38-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="8ee38-104">Sie erstellen eine **DataTable** Objekt mit der entsprechenden **DataTable** Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="8ee38-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="8ee38-105">Hinzuzufügen, können Sie auf die **DataSet** mithilfe der **hinzufügen** Methode zum Hinzufügen der **DataTable** des Objekts **Tabellen** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="8ee38-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="8ee38-106">Können Sie auch erstellen **DataTable** Objekte innerhalb einer **DataSet** mithilfe der **füllen** oder **FillSchema** Methoden der  **DataAdapter** -Objekt, oder aus einem vordefinierten oder abgeleiteten XML-Schema mithilfe der **ReadXml**, **ReadXmlSchema**, oder **InferXmlSchema** Methoden der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="8ee38-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="8ee38-107">Beachten Sie, dass nach dem Hinzufügen von einer **DataTable** als Mitglied der **Tabellen** Auflistung von einem **DataSet**, Sie können nicht auf die Auflistung von Tabellen mit jedem anderen Hinzufügen**DataSet**.</span><span class="sxs-lookup"><span data-stu-id="8ee38-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="8ee38-108">Beim ersten Erstellen einer **DataTable**, er verfügt nicht über ein Schema (d. h. eine Struktur).</span><span class="sxs-lookup"><span data-stu-id="8ee38-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="8ee38-109">Um das Schema der Tabelle zu definieren, müssen Sie erstellen und hinzufügen <xref:System.Data.DataColumn> Objekte die **Spalten** -Auflistung der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8ee38-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="8ee38-110">Sie können auch eine Primärschlüsselspalte für die Tabelle definieren, und erstellen, und fügen **Einschränkung** Objekte die **Einschränkungen** -Auflistung der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8ee38-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="8ee38-111">Nachdem Sie das Schema für definiert haben eine **DataTable**, Sie können Zeilen mit Daten zur Tabelle hinzufügen, durch Hinzufügen von **DataRow** Objekte die **Zeilen** -Auflistung der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8ee38-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="8ee38-112">Sie sind nicht erforderlich, geben Sie einen Wert für die <xref:System.Data.DataTable.TableName%2A> Eigenschaft bei der Erstellung einer **DataTable**; Sie können diese Eigenschaft zu einem späteren Zeitpunkt festlegen, oder Sie lassen ihn leer.</span><span class="sxs-lookup"><span data-stu-id="8ee38-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="8ee38-113">Jedoch beim Hinzufügen einer Tabelle ohne einen **TableName** -Werts in einen **DataSet**, in der Tabelle erhält einen Standardnamen der Tabelle*N*, beginnend mit "Table" für Table0.</span><span class="sxs-lookup"><span data-stu-id="8ee38-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ee38-114">Es wird empfohlen, dass Sie vermeiden, die "Tabelle*N*" Benennungskonvention, wenn Sie angeben einer **TableName** Wert, der der Namen, die Sie angeben, ein Konflikt mit einem bereits vorhandenen Standardtabellennamen im kann die **DataSet** .</span><span class="sxs-lookup"><span data-stu-id="8ee38-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="8ee38-115">Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8ee38-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="8ee38-116">Das folgende Beispiel erstellt eine Instanz von einem **DataTable** -Objekt und weist ihr den Namen "Customers".</span><span class="sxs-lookup"><span data-stu-id="8ee38-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="8ee38-117">Das folgende Beispiel erstellt eine Instanz von einem **DataTable** fügen es zu der **Tabellen** Auflistung von einer **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="8ee38-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ee38-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ee38-118">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [<span data-ttu-id="8ee38-119">DataTables</span><span class="sxs-lookup"><span data-stu-id="8ee38-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="8ee38-120">Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)</span><span class="sxs-lookup"><span data-stu-id="8ee38-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="8ee38-121">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="8ee38-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="8ee38-122">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="8ee38-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="8ee38-123">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="8ee38-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
