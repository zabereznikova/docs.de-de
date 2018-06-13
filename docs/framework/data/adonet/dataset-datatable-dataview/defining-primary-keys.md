---
title: Definieren von Primärschlüsseln
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 21d63aa33e20019f8392b81fb69881296a52cb26
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757579"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="75491-102">Definieren von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="75491-102">Defining Primary Keys</span></span>
<span data-ttu-id="75491-103">Eine Datenbanktabelle enthält i. d. R. eine Spalte oder eine Gruppe von Spalten, die jede Zeile in der Tabelle eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="75491-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="75491-104">Diese identifizierende Spalte oder Spaltengruppe wird als Primärschlüssel bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="75491-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="75491-105">Beim Identifizieren von einer einzelnes <xref:System.Data.DataColumn> als die <xref:System.Data.DataTable.PrimaryKey%2A> für eine <xref:System.Data.DataTable>, setzt die Tabelle automatisch die <xref:System.Data.DataColumn.AllowDBNull%2A> Eigenschaft der Spalte, die **"false"** und die <xref:System.Data.DataColumn.Unique%2A> Eigenschaft  **"true"**.</span><span class="sxs-lookup"><span data-stu-id="75491-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="75491-106">Für den mehrspaltigen Primärschlüssel, nur die **AllowDBNull** -Eigenschaftensatz wird automatisch auf **"false"**.</span><span class="sxs-lookup"><span data-stu-id="75491-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="75491-107">Die **PrimaryKey** Eigenschaft eine <xref:System.Data.DataTable> erhält als Wert ein Array von einem oder mehreren **DataColumn** Objekte, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="75491-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="75491-108">Im ersten Beispiel wird eine einzelne Spalte als Primärschlüssel definiert.</span><span class="sxs-lookup"><span data-stu-id="75491-108">The first example defines a single column as the primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 <span data-ttu-id="75491-109">	Im folgenden Beispiel werden zwei Spalten als Primärschlüssel definiert.</span><span class="sxs-lookup"><span data-stu-id="75491-109">The following example defines two columns as a primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a><span data-ttu-id="75491-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75491-110">See Also</span></span>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="75491-111">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="75491-111">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="75491-112">DataTables</span><span class="sxs-lookup"><span data-stu-id="75491-112">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="75491-113">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="75491-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
