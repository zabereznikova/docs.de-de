---
title: Definieren von Primärschlüsseln
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: dbfd8a8b207c0da9403ac1f8ab36557c4abe383b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204913"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="3c25c-102">Definieren von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="3c25c-102">Defining Primary Keys</span></span>
<span data-ttu-id="3c25c-103">Eine Datenbanktabelle enthält i. d. R. eine Spalte oder eine Gruppe von Spalten, die jede Zeile in der Tabelle eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3c25c-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="3c25c-104">Diese identifizierende Spalte oder Spaltengruppe wird als Primärschlüssel bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3c25c-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="3c25c-105">Wenn Sie einen einzelnen <xref:System.Data.DataColumn> <xref:System.Data.DataColumn.AllowDBNull%2A> <xref:System.Data.DataTable> <xref:System.Data.DataTable.PrimaryKey%2A> als für einen identifizieren, wird die-Eigenschaft der Spalte von der Tabelle automatisch auf **false** festgelegt <xref:System.Data.DataColumn.Unique%2A> , und die-Eigenschaft wird auf **true**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3c25c-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="3c25c-106">Bei mehrspaltigen primär Schlüsseln wird nur die **AllowDBNull** -Eigenschaft automatisch auf **false**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3c25c-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="3c25c-107">Die **PrimaryKey** -Eigenschaft eines <xref:System.Data.DataTable> empfängt als Wert ein Array aus einem oder mehreren **datacolenumn** -Objekten, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c25c-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="3c25c-108">Im ersten Beispiel wird eine einzelne Spalte als Primärschlüssel definiert.</span><span class="sxs-lookup"><span data-stu-id="3c25c-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="3c25c-109">Im folgenden Beispiel werden zwei Spalten als Primärschlüssel definiert.</span><span class="sxs-lookup"><span data-stu-id="3c25c-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3c25c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c25c-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="3c25c-111">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="3c25c-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="3c25c-112">DataTables</span><span class="sxs-lookup"><span data-stu-id="3c25c-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="3c25c-113">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="3c25c-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
