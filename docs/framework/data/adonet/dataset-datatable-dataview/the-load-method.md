---
title: Load-Methode
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150726"
---
# <a name="the-load-method"></a><span data-ttu-id="9dd6f-102">Load-Methode</span><span class="sxs-lookup"><span data-stu-id="9dd6f-102">The Load Method</span></span>
<span data-ttu-id="9dd6f-103">Mithilfe der <xref:System.Data.DataTable.Load%2A>-Methode kann eine <xref:System.Data.DataTable> mit Zeilen aus einer Datenquelle geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="9dd6f-104">Dies ist eine überladene Methode, die in ihrer einfachsten Form einen einzelnen Parameter akzeptiert, einen **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="9dd6f-105">In diesem Formular wird die **DataTable** einfach mit Zeilen geladen.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="9dd6f-106">Optional können Sie den **LoadOption-Parameter** angeben, um zu steuern, wie Daten der **DataTable**hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="9dd6f-107">Der **LoadOption-Parameter** ist besonders nützlich in Fällen, in denen die **DataTable** bereits Datenzeilen enthält, da er beschreibt, wie eingehende Daten aus der Datenquelle mit den daten kombiniert werden, die bereits in der Tabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="9dd6f-108">**PreserveCurrentValues** (Standardeinstellung) gibt beispielsweise an, dass in Fällen, in denen eine Zeile in der **DataTable**als **hinzugefügt** markiert ist, der **Ursprüngliche** Wert oder jede Spalte auf den Inhalt der übereinstimmenden Zeile aus der Datenquelle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="9dd6f-109">Der **aktuelle** Wert behält die Werte bei, die beim Addieren der Zeile zugewiesen wurden, und der **RowState** der Zeile wird auf **Geändert**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="9dd6f-110">Die folgende Tabelle enthält eine kurze Beschreibung der <xref:System.Data.LoadOption>-Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="9dd6f-111">Der LoadOption-Wert</span><span class="sxs-lookup"><span data-stu-id="9dd6f-111">LoadOption value</span></span>|<span data-ttu-id="9dd6f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9dd6f-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="9dd6f-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="9dd6f-113">**OverwriteRow**</span></span>|<span data-ttu-id="9dd6f-114">Wenn eingehende Zeilen denselben **PrimaryKey-Wert** wie eine Zeile haben, die sich bereits in der **DataTable**befindet, werden die **ursprünglichen** und **aktuellen** Werte jeder Spalte durch die Werte in der eingehenden Zeile ersetzt, und die **RowState-Eigenschaft** wird auf **Unchanged**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="9dd6f-115">Zeilen aus der Datenquelle, die noch nicht in der **DataTable** vorhanden sind, werden mit dem **RowState-Wert** **Unchanged**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="9dd6f-116">Diese Option aktualisiert den Inhalt der **DataTable,** sodass sie mit dem Inhalt der Datenquelle übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="9dd6f-117">**PreserveCurrentValues (Standard)**</span><span class="sxs-lookup"><span data-stu-id="9dd6f-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="9dd6f-118">Wenn eingehende Zeilen denselben **PrimaryKey-Wert** wie eine Zeile haben, die sich bereits in der **DataTable**befindet, wird der **Ursprüngliche** Wert auf den Inhalt der eingehenden Zeile festgelegt, und der **aktuelle** Wert wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="9dd6f-119">Wenn **RowState** **hinzugefügt** oder **geändert**wird, wird er auf **Modified**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="9dd6f-120">Wenn der **RowState** **gelöscht**wurde, bleibt er **gelöscht**.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="9dd6f-121">Zeilen aus der Datenquelle, die noch nicht in der **DataTable** vorhanden sind, werden hinzugefügt, und **RowState** wird auf **Unchanged**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="9dd6f-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="9dd6f-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="9dd6f-123">Wenn eingehende Zeilen denselben **PrimaryKey-Wert** wie die Zeile haben, die sich bereits in der **DataTable**befindet, wird der **aktuelle** Wert in den **Ursprünglichen** Wert kopiert, und der **aktuelle** Wert wird dann auf den Inhalt der eingehenden Zeile festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="9dd6f-124">Wenn der **RowState** in der **DataTable** **hinzugefügt**wurde, bleibt der **RowState** **hinzugefügt**.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="9dd6f-125">Für Zeilen, die als **geändert** oder **gelöscht**markiert sind, ist der **RowState** **Modified**.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="9dd6f-126">Zeilen aus der Datenquelle, die noch nicht in der **DataTable** vorhanden sind, werden hinzugefügt, und **RowState** ist auf **Added**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="9dd6f-127">Im folgenden Beispiel wird die **Load-Methode** verwendet, um eine Liste der Geburtstage für die Mitarbeiter in der **Northwind-Datenbank** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9dd6f-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9dd6f-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9dd6f-128">See also</span></span>

- [<span data-ttu-id="9dd6f-129">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="9dd6f-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="9dd6f-130">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9dd6f-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
