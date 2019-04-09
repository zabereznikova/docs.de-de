---
title: Load-Methode
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 82f840ab7dd26a4888ebf024d696f2c70701eb18
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173289"
---
# <a name="the-load-method"></a><span data-ttu-id="9c1e7-102">Load-Methode</span><span class="sxs-lookup"><span data-stu-id="9c1e7-102">The Load Method</span></span>
<span data-ttu-id="9c1e7-103">Mithilfe der <xref:System.Data.DataTable.Load%2A>-Methode kann eine <xref:System.Data.DataTable> mit Zeilen aus einer Datenquelle geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="9c1e7-104">Dies ist eine überladene Methode, die in ihrer einfachsten Form einen einzelnen Parameter akzeptiert eine **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="9c1e7-105">Bei dieser Form lädt sie einfach die **DataTable** mit Zeilen.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="9c1e7-106">Optional können Sie angeben der **LoadOption** Parameter, um zu steuern, wie Daten hinzugefügt werden die **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="9c1e7-107">Die **LoadOption** Parameter ist besonders nützlich in Fällen, in denen die **DataTable** bereits Datenzeilen enthält, da es wird beschrieben, wie die eingehenden Daten aus der Datenquelle wird mit den Daten kombiniert werden bereits in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="9c1e7-108">Z. B. **PreserveCurrentValues** (Standard) gibt an, dass in Fällen, in dem eine Zeile als markiert ist **Added** in die **DataTable**, **ursprünglichen** Wert oder jede Spalte ist auf den Inhalt der entsprechenden Zeile aus der Datenquelle festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="9c1e7-109">Die **aktuelle** -Wert behält die Werte zugewiesen, wenn die Zeile hinzugefügt wurde, und die **RowState** der Zeile festgelegt **Changed**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="9c1e7-110">Die folgende Tabelle enthält eine kurze Beschreibung der <xref:System.Data.LoadOption>-Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="9c1e7-111">Der LoadOption-Wert</span><span class="sxs-lookup"><span data-stu-id="9c1e7-111">LoadOption value</span></span>|<span data-ttu-id="9c1e7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c1e7-112">Description</span></span>|  
|----------------------|-----------------|  
|**<span data-ttu-id="9c1e7-113">OverwriteRow</span><span class="sxs-lookup"><span data-stu-id="9c1e7-113">OverwriteRow</span></span>**|<span data-ttu-id="9c1e7-114">Wenn hinzukommende Zeilen die gleiche haben **PrimaryKey** Wert als eine Zeile, die bereits in der **DataTable**, **ursprünglichen** und **aktuelle** Werte der einzelnen mit den Werten in der eingehenden Zeile, Spalte ersetzt werden und die **RowState** -Eigenschaftensatz auf **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="9c1e7-115">Zeilen aus der Datenquelle, die in noch nicht vorhanden sind die **DataTable** werden hinzugefügt, mit einer **RowState** Wert **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="9c1e7-116">Diese Option wirksam aktualisiert den Inhalt der **DataTable** so, dass sie den Inhalt der Datenquelle übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|**<span data-ttu-id="9c1e7-117">PreserveCurrentValues (Standard)</span><span class="sxs-lookup"><span data-stu-id="9c1e7-117">PreserveCurrentValues (default)</span></span>**|<span data-ttu-id="9c1e7-118">Wenn hinzukommende Zeilen die gleiche haben **PrimaryKey** Wert als eine Zeile, die bereits in der **DataTable**, **ursprünglichen** Wert wird festgelegt, auf den Inhalt der hinzukommenden Zeile, und die **Aktuelle** Wert wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="9c1e7-119">Wenn die **RowState** ist **Added** oder **"geändert"**, festgelegt ist **"geändert"**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="9c1e7-120">Wenn die **RowState** wurde **gelöschte**, bleibt er **gelöschte**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="9c1e7-121">Zeilen aus der Datenquelle, die nicht bereits vorhanden sind in der **DataTable** hinzugefügt werden, und die **RowState** nastaven NA hodnotu **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|**<span data-ttu-id="9c1e7-122">UpdateCurrentValues</span><span class="sxs-lookup"><span data-stu-id="9c1e7-122">UpdateCurrentValues</span></span>**|<span data-ttu-id="9c1e7-123">Wenn hinzukommende Zeilen die gleiche haben **PrimaryKey** Wert wie die Zeile, die bereits in der **DataTable**, **aktuelle** Wert wird in kopiert die **ursprünglichen**Wert und die **aktuelle** Wert wird auf den Inhalt der hinzukommenden Zeile festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="9c1e7-124">Wenn die **RowState** in die **DataTable** wurde **Added**, **RowState** bleibt **Added**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="9c1e7-125">Für Zeilen mit der Markierung **"geändert"** oder **gelöschte**, **RowState** ist **"geändert"**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="9c1e7-126">Zeilen aus der Datenquelle, die in noch nicht vorhanden sind die **DataTable** hinzugefügt werden, und die **RowState** nastaven NA hodnotu **Added**.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="9c1e7-127">Das folgende Beispiel verwendet die **Load** Methode, um eine Liste der Geburtstage für Mitarbeiter im Anzeigen der **Northwind** Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9c1e7-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.   
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c1e7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c1e7-128">See also</span></span>

- [<span data-ttu-id="9c1e7-129">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="9c1e7-129">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="9c1e7-130">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="9c1e7-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
